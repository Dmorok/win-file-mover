# win-file-mover

$filesperfolder = 200
 $sourcePath = "D:\Downloads\"
 $destPath = "D:\Downloads\2sort"
 $folderName = "sort_me_pls"
 $i = 0;
 $folderNum = 1;

 Get-ChildItem "$sourcePath\*.*" | % {
     New-Item -Path ($destPath + "\" + $folderName + $folderNum) -Type Directory -Force
     Move-Item $_ ($destPath + "\" + $folderName + $folderNum);
     $i++;
     if ($i -eq $filesperfolder){
         $folderNum++;
         $i = 0 ;
     }
 }
