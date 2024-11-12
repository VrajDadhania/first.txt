#  **LAB ASSIGNMENT**
---
### 1) Styling text

**BOLD TEXT 1**
__BOLD TEXT 2__
*italic text 1*
_italic text 2_
~~Strikethrough~~
**BOLD and _nested italic_**
***ALL Bold and italic***
This is a <sub>subscript</sub> text
This is a <sup>superscript</sup> text
This is an <ins>underlined</ins> text

### 2)Quoting text
Quoted text give below

> Do or Don't, their is no try

Use `git hub` to list all new or modified files that haven't yet been committed

Make sure you try the following elements:
```
- Headings
- Styling
- Quoting text
- Links
- Images
- Lists (along with task lists)
- Footnotes
- Alerts
- Tables
- Code
- Mathematical Expressions
```

### 3)Linking
you can use chatgpt to inhance this file
https://chatgpt.com/
or you can learn it from [git project](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

### 4)Section Linking


###### Sample Section

###### This'll  be a _Helpful_ Section About the Greek Letter Θ!
A heading containing characters not allowed in fragments, UTF-8 characters, two consecutive spaces between the first and second words, and formatting.

###### This heading is not unique in the file

TEXT 1

###### This heading is not unique in the file

TEXT 2

##### Links to the example headings above

Link to the sample section: [Link Text](#sample-section).

Link to the helpful section: [Link Text](#thisll--be-a-helpful-section-about-the-greek-letter-Θ).

Link to the first non-unique section: [Link Text](#this-heading-is-not-unique-in-the-file).

Link to the second non-unique section: [Link Text](#this-heading-is-not-unique-in-the-file-1).

### 5) Image
![this is an alternative text shown when imag is not properly loded](https://myoctocat.com/assets/images/base-octocat.svg)

### 6) Lists
- George Washington
* John Adams
+ Thomas Jefferson
+ First list item
     - First nested list item
       - Second nested list item
1. James Madison
2. James Monroe
3. John Quincy Adams

task list
- [x] task 1
- [ ] task 2
- [ ]task 3:tada:

Here is a simple footnote[^1].

[^1]: My reference.

### 7)Alerts
> [!NOTE]
> Useful information that users should know, even when skimming content.

> [!TIP]
> Helpful advice for doing things better or more easily.

> [!IMPORTANT]
> Key information users need to know to achieve their goal.

> [!WARNING]
> Urgent info that needs immediate user attention to avoid problems.

> [!CAUTION]
> Advises about risks or negative outcomes of certain actions.


### 8)Code
Below is the python code for dot product
```
import cv2 as cv
import cv2
import numpy as np

def nothing(x):
    pass

cap = cv2.VideoCapture(0);
cv2.namedWindow("tracking")
cv2.createTrackbar("lv","tracking",150,255,nothing)
cv2.createTrackbar("uv","tracking",255,255,nothing)
while(True):
    ret,frame=cap.read()
    #frame=cv.imread("/Users/deepesh/Downloads/50+ Shapes Name in English with Pictures » Onlymyenglish_com.jpg")
    gray=cv2.cvtColor(frame,cv2.COLOR_BGR2GRAY)

    lv=cv2.getTrackbarPos("lv","tracking")
    uv=cv2.getTrackbarPos("uv","tracking")

    canny=cv2.Canny(gray,lv,uv)
    kernel=np.ones((3,3))
    dilated=cv2.dilate(canny,kernel,iterations=1)#removing noise

   # ret,thresh=cv2.threshold(gray,lv,uv,cv2.THRESH_BINARY)
    contours,hierarchy=cv2.findContours(dilated,cv2.RETR_TREE,cv2.CHAIN_APPROX_SIMPLE)

    for contour in contours:
       
       area=cv2.contourArea(contour)
       if area>1000:
        cv2.drawContours(frame,contour,-1,(0,255,0),5)
       peri=cv2.arcLength(contour,True)
       approx=cv2.approxPolyDP(contour,0.01*peri,True)
       x,y,w,h=cv2.boundingRect(approx)
       
       # cv2.rectangle()
       if len(approx)==3:
          #cv2.putText(frame,"Triangle",(x,y),cv2.FONT_HERSHEY_COMPLEX,0.3,(0,0,0))
          cv2.putText(frame,str(len(approx)),(x,y),cv2.FONT_HERSHEY_COMPLEX,0.3,(0,0,0))
       elif len(approx)==4:
          x,y,w,h=cv2.boundingRect(approx)
          asspect=float(w/h)
          if asspect >=0.9 and asspect<=1.1:
           # cv2.putText(frame,"Square",(x,y),cv2.FONT_HERSHEY_COMPLEX,0.3,(0,0,0))
            cv2.putText(frame,str(len(approx)),(x,y),cv2.FONT_HERSHEY_COMPLEX,0.3,(0,0,0))
          else:
            #cv2.putText(frame,"Rectangle",(x,y),cv2.FONT_HERSHEY_COMPLEX,0.3,(0,0,0))
            cv2.putText(frame,str(len(approx)),(x,y),cv2.FONT_HERSHEY_COMPLEX,0.3,(0,0,0))

       elif len(approx)==5:
            #cv2.putText(frame,"Pentagon",(x,y),cv2.FONT_HERSHEY_COMPLEX,0.3,(0,0,0))
            cv2.putText(frame,str(len(approx)),(x,y),cv2.FONT_HERSHEY_COMPLEX,0.3,(0,0,0))
       else:
          #cv2.putText(frame,"circle",(x,y),cv2.FONT_HERSHEY_COMPLEX,0.3,(0,0,0))
          cv2.putText(frame,str(len(approx)),(x,y),cv2.FONT_HERSHEY_COMPLEX,0.3,(0,0,0))


 

    cv2.imshow('canny',canny)
    cv2.imshow('dilate',dilated)
    cv2.imshow('frame',frame)
    if cv2.waitKey(1)&0xFF==ord('q'):
      break





capture.release()
cv.destroyAllWindows()
```
### table

SHAPE
| COLOR | NO COLOR |
| ------ |------ |
| TRIANGLE|SQURE|
| CIRCLE  |
|GOLAA|FOOTBALL |

