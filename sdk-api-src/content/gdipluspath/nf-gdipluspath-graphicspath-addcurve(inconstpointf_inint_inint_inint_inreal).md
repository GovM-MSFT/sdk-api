---
UID: NF:gdipluspath.GraphicsPath.AddCurve(INconstPointF,ININT,ININT,ININT,INREAL)
title: GraphicsPath::AddCurve(IN const PointF,IN INT,IN INT,IN INT,IN REAL) (gdipluspath.h)
description: The GraphicsPath::AddCurve method adds a cardinal spline to the current figure of this path.
helpviewer_keywords: ["AddCurve","AddCurve method [GDI+]","AddCurve method [GDI+]","GraphicsPath class","GraphicsPath class [GDI+]","AddCurve method","GraphicsPath.AddCurve","GraphicsPath.AddCurve(IN const PointF","IN INT","IN INT","IN INT","IN REAL)","GraphicsPath.AddCurve(const PointF*","INT","INT","INT","REAL)","GraphicsPath::AddCurve","GraphicsPath::AddCurve(IN const PointF","IN INT","IN INT","IN INT","IN REAL)","_gdiplus_CLASS_GraphicsPath_AddCurve_PointF_points_INT_count_INT_offset_INT_numberOfSegments_REAL_te","gdiplus._gdiplus_CLASS_GraphicsPath_AddCurve_PointF_points_INT_count_INT_offset_INT_numberOfSegments_REAL_te"]
old-location: gdiplus\_gdiplus_CLASS_GraphicsPath_AddCurve_PointF_points_INT_count_INT_offset_INT_numberOfSegments_REAL_te.htm
tech.root: gdiplus
ms.assetid: VS|gdicpp|~\gdiplus\gdiplusreference\classes\graphicspathclass\graphicspathmethods\graphicspathaddcurvemethods\addcurve_99pointfpoints_intcount_intoffset_intnum.htm
ms.date: 12/05/2018
ms.keywords: AddCurve, AddCurve method [GDI+], AddCurve method [GDI+],GraphicsPath class, GraphicsPath class [GDI+],AddCurve method, GraphicsPath.AddCurve, GraphicsPath.AddCurve(IN const PointF,IN INT,IN INT,IN INT,IN REAL), GraphicsPath.AddCurve(const PointF*,INT,INT,INT,REAL), GraphicsPath::AddCurve, GraphicsPath::AddCurve(IN const PointF,IN INT,IN INT,IN INT,IN REAL), _gdiplus_CLASS_GraphicsPath_AddCurve_PointF_points_INT_count_INT_offset_INT_numberOfSegments_REAL_te, gdiplus._gdiplus_CLASS_GraphicsPath_AddCurve_PointF_points_INT_count_INT_offset_INT_numberOfSegments_REAL_te
req.header: gdipluspath.h
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
 - GraphicsPath::AddCurve
 - gdipluspath/GraphicsPath::AddCurve
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
 - GraphicsPath.AddCurve
---

# GraphicsPath::AddCurve(IN const PointF,IN INT,IN INT,IN INT,IN REAL)


## -description

The <b>GraphicsPath::AddCurve</b> method adds a cardinal spline to the current figure of this path.

## -parameters

### -param points [in]

Type: <b>const <a href="https://docs.microsoft.com/windows/desktop/api/gdiplustypes/nl-gdiplustypes-pointf">PointF</a>*</b>

Pointer to an array of points that define the cardinal spline. The cardinal spline is a curve that passes through a subset (specified by the <i>offset</i> and <i>numberOfSegments</i> parameters) of the points in the array.

### -param count [in]

Type: <b>INT</b>

Integer that specifies the number of elements in the <i>points</i> array.

### -param offset [in]

Type: <b>INT</b>

Integer that specifies the index of the array element that is used as the first point of the cardinal spline.

### -param numberOfSegments [in]

Type: <b>INT</b>

Integer that specifies the number of segments in the cardinal spline. Segments are the curves that connect consecutive points in the array.

### -param tension [in]

Type: <b>REAL</b>

Nonnegative real number that controls the length of the curve and how the curve bends. A value of 0 specifies that the spline is a sequence of straight line segments. As the value increases, the curve becomes fuller.

## -returns

Type: <b><a href="https://docs.microsoft.com/windows/desktop/api/gdiplustypes/ne-gdiplustypes-status">Status</a></b>

If the method succeeds, it returns Ok, which is an element of the <a href="https://docs.microsoft.com/windows/desktop/api/gdiplustypes/ne-gdiplustypes-status">Status</a> enumeration.

If the method fails, it returns one of the other elements of the <a href="https://docs.microsoft.com/windows/desktop/api/gdiplustypes/ne-gdiplustypes-status">Status</a> enumeration.

## -remarks

You should keep a copy of the <i>points</i> array if those points will be needed later. The <a href="https://docs.microsoft.com/windows/desktop/api/gdipluspath/nl-gdipluspath-graphicspath">GraphicsPath</a> object does not store the points passed to the <b>AddClosedCurve</b> method; instead, it converts the cardinal spline to a sequence of Bézier splines and stores the points that define those Bézier splines. You cannot retrieve the original array of points from the <b>GraphicsPath</b> object.


#### Examples



The following example creates a <a href="https://docs.microsoft.com/windows/desktop/api/gdipluspath/nl-gdipluspath-graphicspath">GraphicsPath</a> object <i>path</i>, adds a cardinal spline to <i>path</i>, and then draws <i>path</i>. The spline is built from the points indexed 2 through 6 in an array of eight points.


```cpp
VOID AddCurveExample3(HDC hdc)
{
   Graphics graphics(hdc);
   GraphicsPath path;
   
   PointF pts[] = {PointF(50.0f, 50.0f),
                  PointF(70.0f, 80.0f),
                  PointF(100.0f, 100.0f),
                  PointF(130.0f, 40.0f),
                  PointF(150.0f, 90.0f),
                  PointF(180.0f, 30.0f),
                  PointF(210.0f, 120.0f),
                  PointF(240.0f, 80.0f)};
   path.AddCurve(
      pts, 
      8,     // There are eight points in the array. 
      2,     // Start at the point with index 2.
      4,     // Four segments. End at the point with index 6.
      1.0f);
   Pen pen(Color(255, 0, 0, 255));
   graphics.DrawPath(&pen, &path);
   // Draw all eight points in the array.
   SolidBrush brush(Color(255, 255, 0, 0));
   for(INT j = 0; j <= 7; ++j)
      graphics.FillEllipse(&brush, pts[j].X - 3.0f, pts[j].Y - 3.0f, 6.0f, 6.0f); 
}
Color(255, 255, 0,  0)
```

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/api/gdipluspath/nf-gdipluspath-graphicspath-addbezier(inconstpoint__inconstpoint__inconstpoint__inconstpoint_)">AddBezier Methods</a>



<a href="https://docs.microsoft.com/windows/desktop/api/gdipluspath/nf-gdipluspath-graphicspath-addbeziers(inconstpoint_inint)">AddBeziers Methods</a>



<a href="https://docs.microsoft.com/windows/desktop/api/gdipluspath/nf-gdipluspath-graphicspath-addclosedcurve(inconstpointf_inint_inreal)">AddClosedCurve Methods</a>



<a href="https://docs.microsoft.com/windows/desktop/api/gdipluspath/nf-gdipluspath-graphicspath-addcurve(inconstpointf_inint_inint_inint_inreal)">AddCurve Methods</a>



<a href="https://docs.microsoft.com/windows/desktop/gdiplus/-gdiplus-cardinal-splines-about">Cardinal Splines</a>



<a href="https://docs.microsoft.com/windows/desktop/gdiplus/-gdiplus-clipping-with-a-region-use">Clipping with a Region</a>



<a href="https://docs.microsoft.com/windows/desktop/gdiplus/-gdiplus-constructing-and-drawing-paths-use">Constructing and Drawing Paths</a>



<a href="https://docs.microsoft.com/windows/desktop/gdiplus/-gdiplus-creating-a-path-gradient-use">Creating a Path Gradient</a>



<a href="https://docs.microsoft.com/windows/desktop/gdiplus/-gdiplus-drawing-cardinal-splines-use">Drawing Cardinal Splines</a>



<a href="https://docs.microsoft.com/windows/desktop/api/gdipluspath/nl-gdipluspath-graphicspath">GraphicsPath</a>



<a href="https://docs.microsoft.com/windows/desktop/gdiplus/-gdiplus-paths-about">Paths</a>



<a href="https://docs.microsoft.com/windows/desktop/api/gdiplustypes/nl-gdiplustypes-pointf">PointF</a>

