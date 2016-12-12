Na aplicação android havia uma opção de tirar uma fotografia diretamente da aplicação e dar upload para uma pasta. Assim, nós pensámos que a implementação de tirar um vídeo diretamente da aplicação, embora não estar na "wishlist" deles, enquadrava-se na aplicação.
A nível de código, com os trabalhos passados, tinhamos ligeiramente noção onde eram implementadas certas funcionalidades, sendo a que nos interessava era uma função do browser que era tirar uma foto, assim fomos ver o exemplo de código que permitia tirar uma fotografia e orientámo-nos por aí.
A partir do código base fomos pesquisar o que seria necessário alterar para criar esta nova feature.

Começamos por adicionar um botão na lista de opções de add para começar a filmar.

```java
private void addFile() {
        final AlertDialog.Builder builder = new AlertDialog.Builder(this);
        builder.setTitle(getString(R.string.add_file));
        builder.setItems(R.array.add_file_options_array, new DialogInterface.OnClickListener() {
            @Override
            public void onClick(DialogInterface dialog, int which) {
                if (which == 0) // create file
                    showNewFileDialog();
                else if (which == 1) // create folder
                    showNewDirDialog();
                else if (which == 2) // upload file
                    pickFile();
                else if (which == 3) // take a photo
                    CameraTakePhoto();
                else if (which == 4) // capture a video
                    CameraCaptureVideo();
            }
        }).show();
    }
    
``` 

De seguida, com base no código que eles já tinham para tirar uma fotografia, criamos uma função para fazer um vídeo, como podemos ver nos seguintes blocos de código:
```java
private File takeCameraPhotoTempFile;

    private void CameraTakePhoto() {
        Intent imageCaptureIntent = new Intent("android.media.action.IMAGE_CAPTURE");

        try {
            File ImgDir = DataManager.createTempDir();

            String fileName = new SimpleDateFormat("yyyyMMddHHmmss").format(new Date()) + ".jpg";
            takeCameraPhotoTempFile = new File(ImgDir, fileName);

            Uri photo = Uri.fromFile(takeCameraPhotoTempFile);
            imageCaptureIntent.putExtra(MediaStore.EXTRA_OUTPUT, photo);
            startActivityForResult(imageCaptureIntent, TAKE_PHOTO_REQUEST);

        } catch (IOException e) {
            showShortToast(BrowserActivity.this, R.string.unknow_error);
        }
    }
    
```   

```java

private File captureCameraVideoTempFile;

    private void CameraCaptureVideo() {
        Intent videoCaptureIntent = new Intent("android.media.action.VIDEO_CAPTURE");

        try {
            File VideoDir = DataManager.createTempDir();

            String fileName = new SimpleDateFormat("yyyyMMddHHmmss").format(new Date()) + ".mp4";
            captureCameraVideoTempFile = new File(VideoDir, fileName);

            Uri video = Uri.fromFile(captureCameraVideoTempFile);
            videoCaptureIntent.putExtra(MediaStore.EXTRA_OUTPUT, video);
            startActivityForResult(videoCaptureIntent, CAPTURE_VIDEO_REQUEST);

        } catch (IOException e) {
            showShortToast(BrowserActivity.this, R.string.unknow_error);
        }
    }
```

```java

case TAKE_PHOTO_REQUEST:
            if (resultCode == RESULT_OK) {
                showShortToast(this, getString(R.string.take_photo_successfully));
                if (!Utils.isNetworkOn()) {
                    showShortToast(this, R.string.network_down);
                    return;
                }

                if(takeCameraPhotoTempFile == null) {
                    showShortToast(this, getString(R.string.saf_upload_path_not_available));
                    Log.i(DEBUG_TAG, "Pick file request did not return a path");
                    return;
                }
                showShortToast(this, getString(R.string.added_to_upload_tasks));
                final SeafRepo repo = dataManager.getCachedRepoByID(navContext.getRepoID());
                if (repo != null && repo.canLocalDecrypt()) {
                    addUploadBlocksTask(navContext.getRepoID(), navContext.getRepoName(), navContext.getDirPath(), takeCameraPhotoTempFile.getAbsolutePath(), repo.encVersion);
                } else {
                    addUploadTask(navContext.getRepoID(), navContext.getRepoName(), navContext.getDirPath(), takeCameraPhotoTempFile.getAbsolutePath());
                }

            }
            break;
            
```   

```java
case CAPTURE_VIDEO_REQUEST:
                if (resultCode == RESULT_OK) {
                    showShortToast(this, getString(R.string.capture_video_successfully));
                    if (!Utils.isNetworkOn()) {
                        showShortToast(this, R.string.network_down);
                        return;
                    }

                    if(captureCameraVideoTempFile == null) {
                        showShortToast(this, getString(R.string.saf_upload_path_not_available));
                        Log.i(DEBUG_TAG, "Pick file request did not return a path");
                        return;
                    }
                    showShortToast(this, getString(R.string.added_to_upload_tasks));
                    final SeafRepo repo = dataManager.getCachedRepoByID(navContext.getRepoID());
                    if (repo != null && repo.canLocalDecrypt()) {
                        addUploadBlocksTask(navContext.getRepoID(), navContext.getRepoName(), navContext.getDirPath(), captureCameraVideoTempFile.getAbsolutePath(), repo.encVersion);
                    } else {
                        addUploadTask(navContext.getRepoID(), navContext.getRepoName(), navContext.getDirPath(), captureCameraVideoTempFile.getAbsolutePath());
                    }

                }
                break;
