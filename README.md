# ocr-tests

## Test 1:

The diff between the actual text (left) and the OCR result ([json](https://github.com/ngawangtrinley/ocr-tests/blob/653c4418ceef6066c299d824677c5a5c1724129e/google-vision/test1/response.json)) of [this image](https://www.tbrc.org/browser/ImageService?work=W1PD95844&igroup=I1PD95940&image=25&first=23&last=636&fetchimg=yes) (right)...


<iframe src="http://prose.io/#ngawangtrinley/starter"></iframe>



https://github.com/ngawangtrinley/ocr-tests/compare/f0035c4...3baffd5

...highlights several types of issues:

- '༥' 0f25, at the end of the header [wasn't detected](https://github.com/ngawangtrinley/ocr-tests/blob/master/google-vision/test1/59616523_1021243074750126_1267057790891851776_n.png), but somehow an extra '།' 0f0d appeared at [the end of the text](https://github.com/ngawangtrinley/ocr-tests/compare/f0035c4...3baffd5#diff-0b4da83768e1849331590454147c62d3R1)
- '࿒' 0FD2 is replaced by a ':' 003a at the start of lines, and by '་' 0f0b in [the middle of lines](https://github.com/ngawangtrinley/ocr-tests/compare/f0035c4...3baffd5#diff-0b4da83768e1849331590454147c62d3R7)
- 'ཿ' 0f7f are ignored
- Tibetan enclosed alphanumerics (replaced by ①...) aren't detected at all. The reason most probably being that these aren't part of the Tibetan Unicode table
- a '་' 0f0b has been added between two sentences in [line 18](https://github.com/ngawangtrinley/ocr-tests/compare/f0035c4...3baffd5#diff-0b4da83768e1849331590454147c62d3R18), most probably [from the text on the backside of the page](https://github.com/ngawangtrinley/ocr-tests/blob/master/google-vision/test1/59616523_1021243074750126_1267057790891851776_n.png).
- the remaining issues are letter combinations used in transliterating sanskrit (very common in buddhist literature) and that might not have featured in training data...
