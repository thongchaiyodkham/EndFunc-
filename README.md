# EndFunc-
 ; #FUNCTION# ==================================================================================================================== ; Name ..........: _StringExtractPath ; Description ...: Extracts the paths from a text and return an array of paths. ; Syntax ........: _StringExtractPath($sText) ; Parameters ....: $sText               - The String to extract the paths from. ; Return values .: 1D Array of paths. Array[0] contains the number of paths found. ; Author ........: Jmon ; Modified ......: ; Remarks .......: ; Related .......: ; Link ..........: ; Example .......: Yes ; =============================================================================================================================== Func _StringExtractPath($sText)     Local $aRet[1] = [0], $a     $a = StringRegExp($sText, '(?i)((?:(?:https?|rtp|mms|rtsp|file|ftps?)\:)?[\\|\/]{2}[\w-_]*[\w\\\/?&amp;=.~;\-+!*_#%]*)|([a-z]:[\\\/][\w\.-_\\\/]*)|(w{3}\.[\w\\\/?&amp;=.~;\-+!*_#%]*)', 3)     If @error = 0 Then         For $i = 0 To UBound($a) - 1             If $a[$i] &lt;> "" Then                 $aRet[0] += 1                 ReDim $aRet[$aRet[0] + 1]                 $aRet[$aRet[0]] = $a[$i]             EndIf         Next     EndIf     Return $aRet EndFunc   ;==>_StringExtractPath
