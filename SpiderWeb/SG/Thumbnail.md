[[Imagick]]
[[Thumbnail Q&A]] 
raster image: pixels, jpeg, png, gif, resolution dependent
vector image: math ,svg, eps, pdf, resolution independent
optimize image: reduce size, format, lazy load,...
webp, small size, transparency as PNG, lossless, lossy, page speed
gif to webp: FFMPEG tool
overhead time: context switching, memory management, garbage collection, synchronization
context switching: stop thread/process -> run another -> save old, load new
source base: imageproxy
--------------------------
 [https://jira.smilegate.net/browse/SGVTN-4086](https://jira.smilegate.net/browse/SGVTN-4086 "https://jira.smilegate.net/browse/sgvtn-4086")  
[https://wiki.smilegate.net/display/SWSD/WDF03.07.04.13+file+extension+convert](https://wiki.smilegate.net/display/SWSD/WDF03.07.04.13+file+extension+convert "https://wiki.smilegate.net/display/swsd/wdf03.07.04.13+file+extension+convert")  
[https://wiki.smilegate.net/pages/viewpage.action?pageId=432336091](https://wiki.smilegate.net/pages/viewpage.action?pageId=432336091 "https://wiki.smilegate.net/pages/viewpage.action?pageid=432336091")  
[https://wiki.smilegate.net/display/SGVTN/06.+Investigate+gif+-%3E+apng+or+webp](https://wiki.smilegate.net/display/SGVTN/06.+Investigate+gif+-%3E+apng+or+webp "https://wiki.smilegate.net/display/sgvtn/06.+investigate+gif+-%3e+apng+or+webp")  
[https://github.com/gographics/imagick](https://github.com/gographics/imagick "https://github.com/gographics/imagick")  
[https://jira.smilegate.net/browse/STONPMS-44754](https://jira.smilegate.net/browse/STONPMS-44754 "https://jira.smilegate.net/browse/stonpms-44754")

**#I. Go module convert image:**  
Lib: imagick

1) heif/heic → jpg  
2) gif/png/jpg/jpeg -> webp  
3) animated gif -> webm or apng  
API: contract: [https://wiki.smilegate.net/pages/viewpage.action?pageId=432336091](https://wiki.smilegate.net/pages/viewpage.action?pageId=432336091 "https://wiki.smilegate.net/pages/viewpage.action?pageid=432336091")  
[https://github.com/gographics/imagick](https://github.com/gographics/imagick "https://github.com/gographics/imagick")

**#II. Animated gif -> webm or apng**  
Research animated gif  -> webm or apng  
+ lib: ??  
+ test images

[[pkg-config]] compiler, linker program with library
[[file path]] ./, ../