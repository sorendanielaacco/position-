# position-
;~ I have not tested this code yet, but you can use something like this Func _HandleMultiImgSearch($hwnd, $ImgsPath, $x = 0, $y = 0, $iWidth = -1, $iHeight = -1, $Tolerance = 15, $MaxImg = 1000)     Local ImgsPathArray = StringSplit($ImgsPath, "|", 2) ;$ImgsPath = 'Path1|Path2|...|PathN'     Local $Results     For ImgPath in ImgsPathArray         $Results = _ArrayAdd($Result, _HandleImgSearch($hwnd, $ImgPath, $x, $y, $iWidth, $iHeight, $Tolerance, $MaxImg))     Next          Return $Results EndFunc  ;~ Using this func Local $ImgsPath = 'a.png|b.png|c.png' Local $Results = _HandleMultiImgSearch($hwnd, $ImgsPath) ConsoleWrite("> Total of finding images: " &amp; Ubound($Results)) Local $count = 0 For $Coords in $Results     ;~ An array of positions of each image     $count += 1     ConsoleWrite(">> Total of position found of image " &amp; $count &amp; " found: " &amp; Ubound($Coords[0][0]))
