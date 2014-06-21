Get-MicrosoftUpdate
===================

Shows all Microsoft Updates, not just Windows Updates like Get-HotFix

http://lyncdup.com/2013/09/list-all-microsoftwindows-updates-with-powershell-sorted-by-kbhotfixid-get-microsoftupdate/

I recently came across a scenario where I needed to check if certain Hotfixes for Microsoft Office were installed. 
Easy, Get-HotFix right?

Get-HotFix | Sort-Object HotFixID | Format-Table –AutoSize

Unfortunately this only shows Windows Updates, not all *Microsoft Updates* for example 
Microsoft Application Updates, Drivers etc..

A quick search lead me here: http://blogs.technet.com/b/tmintner/archive/2006/07/07/440729.aspx, 
which shows how to get a list of updates, but unfortunately the HotFixID/KB isn’t held as a property, 
so the output isn’t much better than just scrolling through the endless list of Installed Updates in the GUI


However with a little Regex and Select-String magic this script grabs the HotfixID/KB and sorts the output by it.
