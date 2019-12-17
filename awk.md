### AWK的用法


* AWK求和  
```
ls -l |grep -v total | awk '{sum+=$5' END {print "sum=", sum}'
```


* AWK求平均  
```
ls -l |grep -v total | awk '{sum+=$5 END {print "avg=", sum/NR}'
```


* AWK求最大值  
```
ls -l |grep -v total |awk 'BEGIN {max=0} {if($5>max) max=$5} END {print "max=", max}'
```


* AWK求最小值  
```
ls -l |grep -v total | awk 'BEGIN {min=19999999} {if($5<min) min=$5} END {print "min=", min}'
```



