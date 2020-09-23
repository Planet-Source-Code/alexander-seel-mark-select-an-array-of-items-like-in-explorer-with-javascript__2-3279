<div align="center">

## Mark\(Select\) an Array of Items like in Explorer with Javascript


</div>

### Description

Select Items on a HTML Page like selecting (mark) Files in a Explorer Window by holding down the Mouse Button an move over the items.
 
### More Info
 
The marked items


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Alexander Seel](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/alexander-seel.md)
**Level**          |Intermediate
**User Rating**    |5.0 (10 globes from 2 users)
**Compatibility**  |
**Category**       |[Miscellaneous](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/miscellaneous__2-57.md)
**World**          |[Java](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/java.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/alexander-seel-mark-select-an-array-of-items-like-in-explorer-with-javascript__2-3279/archive/master.zip)





### Source Code

```

<HTML>
<SCRIPT LANGUAGE="Javascript">
var xPos = 0;
var yPos = 0;
var bMark = false;
function bodyMouseDown()
{
	var sDiv ='';
	if (!document.all.divMark)
	{
		sDiv ="<DIV ID='divMark' NAME='divMark' style='border:solid;border-Width:1px;border-Color: #666666;background-Color: #ddddee;Filter:alpha(opacity=75)'></DIV>";
		document.body.insertAdjacentHTML("BeforeEnd",sDiv);
		document.all.item("divMark").style.position = "absolute";
		document.all.item("divMark").style.posTop = event.clientX;
		document.all.item("divMark").style.posLeft = event.clientY;
	}
	xPos = event.clientX;
	yPos = event.clientY;
	bMark = true;
}
function bodyMouseUp()
{
	var lMax = document.body.all.length;
	var sSelected="";
	var lCount = 0;
	var lMaxLeft = document.all.item("divMark").offsetLeft-20;
	var lMaxRight = lMaxLeft + document.all.item("divMark").offsetWidth+20;
	var lMaxTop = document.all.item("divMark").offsetTop-20;
	var lMaxBottom = lMaxTop + document.all.item("divMark").offsetHeight+20;
	while (lCount<lMax)
	{
		var obj = document.body.all.item(lCount);
		var lLeft = obj.offsetLeft;
		var lRight = obj.offsetLeft+obj.offsetWidth;
		var lTop = obj.offsetTop;
		var lBottom = lTop+obj.offsetHeight;
		if((lMaxLeft<lLeft) && (lMaxRight>lRight) && (lMaxTop<lTop) && (lMaxBottom>lBottom))
		{
			sSelected=sSelected +obj.innerHTML +":";
		}
		lCount++;
	}
	bMark = false;
	alert('You selected :' + sSelected);
}
function bodyMouseMove()
{
var xMouse=event.clientX;
var yMouse=event.clientY;
	if (bMark==true)
	{
		if (xMouse<xPos)
		{
			document.all.item("divMark").style.posLeft=xMouse;
			document.all.item("divMark").style.width=xPos-xMouse;
		}
		else
		{
			document.all.item("divMark").style.posLeft=xPos;
			document.all.item("divMark").style.width=xMouse-xPos;
		};
		if (yMouse<yPos)
		{
			document.all.item("divMark").style.posTop=yMouse;
			document.all.item("divMark").style.height=yPos-yMouse;
		}
		else
		{
			document.all.item("divMark").style.posTop=yPos;
			document.all.item("divMark").style.height=yMouse-yPos;
		};
	};
}
</SCRIPT>
<BODY onMouseDown="bodyMouseDown()" onMouseUp="bodyMouseUp()" onMouseMove="bodyMouseMove()">
<div align="center">
 <center>
<table border="1" cellpadding="0" cellspacing="0" style="border-collapse: collapse" bordercolor="#111111" height="100%" width="100%" id="AutoNumber1">
 <tr>
  <td width="25%" align="center" bgcolor="#C0C0C0">Column 1 Row 1</td>
  <td width="25%" align="center" bgcolor="#FFFF99">Column 2 Row 1</td>
  <td width="25%" align="center" bgcolor="#C0C0C0">Column 3 Row 1</td>
  <td width="25%" align="center" bgcolor="#FFFF99">Column 4 Row 1</td>
 </tr>
 <tr>
  <td width="25%" align="center" bgcolor="#FFFF99">Column 1 Row 2</td>
  <td width="25%" align="center" bgcolor="#C0C0C0">Column 2 Row 2</td>
  <td width="25%" align="center" bgcolor="#FFFF99">Column 3 Row 2</td>
  <td width="25%" align="center" bgcolor="#C0C0C0">Column 4 Row 2</td>
 </tr>
 <tr>
  <td width="25%" align="center" bgcolor="#C0C0C0">Column 1 Row 3</td>
  <td width="25%" align="center" bgcolor="#FFFF99">Column 2 Row 3</td>
  <td width="25%" align="center" bgcolor="#C0C0C0">Column 3 Row 3</td>
  <td width="25%" align="center" bgcolor="#FFFF99">Column 4 Row 3</td>
 </tr>
 <tr>
  <td width="25%" align="center" bgcolor="#FFFF99">Column 1 Row 4</td>
  <td width="25%" align="center" bgcolor="#C0C0C0">Column 2 Row 4</td>
  <td width="25%" align="center" bgcolor="#FFFF99">Column 3 Row 4</td>
  <td width="25%" align="center" bgcolor="#C0C0C0">Column 4 Row 4</td>
 </tr>
</table>
 </center>
</div>
</BODY>
</HTML>
```

