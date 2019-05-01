# ocr-tests
OCR test 


Test 1:

The diff between the OCR result of [this image](https://www.tbrc.org/browser/ImageService?work=W1PD95844&igroup=I1PD95940&image=25&first=23&last=636&fetchimg=yes) ([json](https://github.com/ngawangtrinley/ocr-tests/blob/653c4418ceef6066c299d824677c5a5c1724129e/google-vision/test1/response.json)) and the actual text...

https://github.com/ngawangtrinley/ocr-tests/compare/653c441...e834088

...highlights several types of issues.

- '࿒' 0FD2 is replaced by a ':' 003a at the start of lines, and by '་' 0f0b in the middle of lines
- Tibetan enclosed alphanumerics aren't detected at all. The reason most probably being that these aren't part of the Tibetan Unicode table
- a '་' 0f0b has been added on [line 18](https://github.com/ngawangtrinley/ocr-tests/blob/e83408897c332c0c1f6451a752ef7f50c166e819/google-vision/test1/diff.txt#L18), most probably from the text on the backside of the page.
- the remaining issues are letter combinations used in transliterating sanskrit and that might not have featured in training data.
