##Grep

###Extracting build summary
```
cat -n hist.log | grep 21355bb  
head -48 hist.log | grep -aoe "[0-9] | .*" | grep -aoP "(?<=\| ).*" | grep -v Merge | sort -u > commits.log  
less commits.log | grep -vP ".*(Surname1)|(Surname2)+.*" > split1.log  
```

###No color
``` 
grep --color=never  
```

###Extract values
```
grep -aoe "5177=/w*" fix.log | sort -u | less
egrep -ao "5177=/w*" fix.log | sort -u | less
```

###Find values
```
grep -a "BestBid" ./instance*/fix*.log | less
```

###Find string recursively in folder then extract it and display sorted distinct values
```
grep -r "fix.version" . | grep -aoe "fix/.version/s*=/s*4/.[0-9]" | sort | uniq | less
```

###Find string recursively in folder given file name pattern
```
grep -r --include="*.log" "8=FIX/.4/.[0-9]" .
```

###Find free BASE_PORT
```
grep -iR BASE_PORT ./config/EU/ | grep -aoe "/{BASE_PORT/}".* | sort
    -i (-y, --ignore-case) - Ignore case distinctions, so that characters that differ only in case match each other. 
    -R (--dereference-recursive) - For each directory operand, read and process all files in that directory, recursively, following all symbolic links.
```

###List files NOT matching a pattern
```
ls | grep -v '/.jar$'
```

###Diff greps
```
diff <(grep "XXX" myfile1) <(grep "XXX" myfile2)
```
