##Grep
cat -n hist.log | grep 21355bb
head -48 hist.log | grep -aoe "[0-9] | .*" | grep -aoP "(?<=\| ).*" | grep -v Merge | sort -u > commits.log
less commits.log | grep -vP ".*(Surname1)|(Surname2)+.*" > split1.log
