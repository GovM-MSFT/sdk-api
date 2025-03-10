---
UID: NF:gdiplustypes.Point.operator-add
title: Point::operator-add (gdiplustypes.h)
description: The Point::operator+ method adds the X and Y data members of two Point objects.
helpviewer_keywords: ["Point class [GDI+]","operator+ method","Point.operator+","Point.operator+(const Point&)","Point.operator-add","Point::operator+","Point::operator-add","_gdiplus_CLASS_Point_operator_opadd_point_","gdiplus._gdiplus_CLASS_Point_operator_opadd_point_","operator+","operator+ method [GDI+]","operator+ method [GDI+]","Point class"]
old-location: gdiplus\_gdiplus_CLASS_Point_operator_opadd_point_.htm
tech.root: gdiplus
ms.assetid: VS|gdicpp|~\gdiplus\gdiplusreference\classes\pointclass\pointmethods\operatorplus.htm
ms.date: 12/05/2018
ms.keywords: Point class [GDI+],operator+ method, Point.operator+, Point.operator+(const Point&), Point.operator-add, Point::operator+, Point::operator-add, _gdiplus_CLASS_Point_operator_opadd_point_, gdiplus._gdiplus_CLASS_Point_operator_opadd_point_, operator+, operator+ method [GDI+], operator+ method [GDI+],Point class
req.header: gdiplustypes.h
req.include-header: Gdiplus.h
req.target-type: Windows
req.target-min-winverclnt: Windows XP, Windows 2000 Professional [desktop apps only]
req.target-min-winversvr: Windows 2000 Server [desktop apps only]
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Gdiplus.lib
req.dll: Gdiplus.dll
req.irql: 
targetos: Windows
req.typenames: 
req.redist: 
req.product: GDI+ 1.0
ms.custom: 19H1
f1_keywords:
 - Point::operator+
 - gdiplustypes/Point::operator+
dev_langs:
 - c++
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - Gdiplus.dll
api_name:
 - Point.operator+
---

# Point::operator-add


## -description

The <b>Point::operator+</b> method adds the <b>X</b> and <b>Y</b> data members of two <a href="https://docs.microsoft.com/windows/desktop/api/gdiplustypes/nl-gdiplustypes-point">Point</a> objects.

## -parameters

### -param point [in, ref]

Type: <b>const <a href="https://docs.microsoft.com/windows/desktop/api/gdiplustypes/nl-gdiplustypes-point">Point</a></b>

Reference to a <a href="https://docs.microsoft.com/windows/desktop/api/gdiplustypes/nl-gdiplustypes-point">Point</a> object whose <b>X</b> and <b>Y</b> data members are added to the <b>X</b> and <b>Y</b> data members of this <b>Point</b> object.

## -returns

Type: <b><a href="https://docs.microsoft.com/windows/desktop/api/gdiplustypes/nl-gdiplustypes-point">Point</a></b>

This method returns a <a href="https://docs.microsoft.com/windows/desktop/api/gdiplustypes/nl-gdiplustypes-point">Point</a> object that is the sum of two <b>Point</b> objects.

## -remarks

This method overloads the addition operator for <a href="https://docs.microsoft.com/windows/desktop/api/gdiplustypes/nl-gdiplustypes-point">Point</a> objects. If A, B, and C are <b>Point</b> objects, the statement <b>C = A + B</b> is equivalent to <b>C = A.operator+(B)</b>.


#### Examples



The following example creates two <a href="https://docs.microsoft.com/windows/desktop/api/gdiplustypes/nl-gdiplustypes-point">Point</a> objects, then adds the two <b>Point</b> objects and stores the result in a third <b>Point</b> object.


```cpp
Point point1(40, 10);
Point point2(20, 30);

// Point 3 now contains the coordinates (60, 40).
Point point3 = point1 + point2; 
```

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/api/gdiplustypes/nl-gdiplustypes-point">Point</a>



<a href="https://docs.microsoft.com/windows/desktop/api/gdiplustypes/nf-gdiplustypes-point-equals">Point::Equals</a>



<a href="https://docs.microsoft.com/previous-versions/ms535009(v=vs.85)">Point::operator-</a>



<a href="https://docs.microsoft.com/windows/desktop/api/gdiplustypes/nl-gdiplustypes-pointf">PointF</a>

