# -EndIf-
_WD_NewTab($sSession, $lSwitch = True)     Local Const $sFuncName = "_WD_NewTab"     Local $sTabHandle = ''      _WD_ExecuteScript($sSession, 'window.open()', '{}')      If @error = $_WD_ERROR_Success Then         Local $aHandles = _WD_Window($sSession, 'handles', '')                  $sTabHandle = $aHandles[UBound($aHandles) - 1] ;&lt;&lt;&lt;&lt;&lt;&lt;&lt;&lt;&lt;&lt;&lt;&lt;&lt;&lt;&lt;&lt;&lt;&lt;&lt;&lt;&lt;&lt;If this is no array, script interrupt          If $lSwitch Then             _WD_Window($sSession, 'Switch', '{"handle":"' &amp; $sTabHandle &amp; '"}')         EndIf     EndIf      Return SetError($_WD_ERROR_Success, 0, $sTabHandle) EndFunc   Func _WD_NewTab($sSession, $lSwitch = True)     Local Const $sFuncName = "_WD_NewTab"     Local $sTabHandle = ''      _WD_ExecuteScript($sSession, 'window.open()', '{}')      If @error = $_WD_ERROR_Success Then         Local $aHandles = _WD_Window($sSession, 'handles', '')           If IsArray($aHandles) Then         $sTabHandle = $aHandles[UBound($aHandles) - 1]           Else             ConsoleWrite("> An error occurred. " &amp; 'No Session exist.' &amp; @CRLF)         EndIf          If $lSwitch Then             _WD_Window($sSession, 'Switch', '{"handle":"' &amp; $sTabHandle &amp; '"}')         EndIf     EndIf      Return SetError($_WD_ERROR_Success, 0, $sTabHandle) EndFunc
