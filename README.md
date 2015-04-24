# android-file-dialog
Automatically exported from code.google.com/p/android-file-dialog

The standard API does not include file dialog to select files or directories. 
This library is a file dialog that currently supports file selection and creation. 
In the near future it will also support directory selection - This functionality was added by cirelli.mauricio and commited to trunk as FileDialogWithDirectories.java.

The dialog is an Activity. It just returns you the path to the file that user has chosen. It doesn't create nor open files, the library only returns paths in such form "/sdcard/temp/file.txt". You are free to make whatever you like with the given path.



The dialog is created like this:

                Intent intent = new Intent(getBaseContext(), FileDialog.class);
                intent.putExtra(FileDialog.START_PATH, "/sdcard");
                
                //can user select directories or not
                intent.putExtra(FileDialog.CAN_SELECT_DIR, true);
                
                //alternatively you can set file filter
                //intent.putExtra(FileDialog.FORMAT_FILTER, new String[] { "png" });
                
                startActivityForResult(intent, REQUEST_SAVE);
