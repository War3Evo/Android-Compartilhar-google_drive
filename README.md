Modified from original in english

- The KastriFree library DW.Androidapi.JNI.Provider.pas file must be updated to work on current Android versions.
  Line 28 which contains:
  [JavaSignature('android/support/v4/content/FileProvider')]
  It must be replaced by:
  [JavaSignature('androidx/core/content/FileProvider')]

- In Project > Options > Application > Entitlement List
  The "Secure File Sharing" option must be set to "true"
  This will automatically include the information below in AndroidManifest.xml:

  
   
  
    
  
   

  This provider is required for newer versions of Android to access the uploaded file.
  The provider-paths.xml is also created and automatically added to Projects > Deployment.

  This application has the "findMimeType" function that identifies
  automatically the file type accepted by the JIntent directive (example below).
  intent.setDataAndType(URI, StringToJString('FileType'));

  For your information, only the file types ('FileType') listed below are supported:
  image/jpeg
  audio/mpeg4-generic
  text/html
  audio/mpeg
  audio/aac
  audio/wav
  audio/ogg
  audio/midi
  audio/x-ms-wma
  video/mp4
  video/x-msvideo
  video/x-ms-wmv
  image/png
  image/jpeg
  image/gif
  .xml ->text/xml
  .txt -> text/plain
  .cfg -> text/plain
  .csv -> text/plain
  .conf -> text/plain
  .rc -> text/plain
  .htm -> text/html
  .html -> text/html
  .pdf -> application/pdf
  .apk -> application/vnd.android.package-archive
