This fork adds multiple connections incremental downloading to axel.

It's based on "[reactivation](https://github.com/emiraga/axel)" branch of Emir Habul.

Instead of downloading the file in big chunks (the default), it has the following strategy:
* it downloads the file in small chunks, 5 megabytes or smaller 
* starting from beggining of the file

## Why is this useful ?
Some files like videos could be played before the download is finished we just need to adopt a correct chunk-cutting strategy. It's exactly what axel-incremental-downloading is doing.

Now you don't need to wait for a video to finish to download, you can start watching it directly.

## Testing
I downloaded on a 700 meg file from a remote host, the hash matched the original file. Testing platform: MacOSX

## Building on MacOSX
./configure --prefix=/opt/local --i18n=1 
make -j8 -w all CFLAGS="-O2 -arch x86_64 -I/opt/local/include" LFLAGS="-L/opt/local/lib -lintl -liconv"

## Author
Nicolae Namolovan


Feel free to fork and improve.