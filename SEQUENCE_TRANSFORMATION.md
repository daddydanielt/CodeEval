__CodeEval Challenage:__

[SEQUENCE TRANSFORMATION](https://www.codeeval.com/open_challenges/130/)

__Below is thinking note & psuedo code:__

# -

1010 AAAAABBBBAAAA

A 010  => AAAABBBBAAAA

A AAAA 10 => BBBBAAAA

A AAAA BBBB 0 => AAAA

#
00 AAAAAA 

[0,0] [A=>6]

[0,0] [A=>1, A=>5]


0) 元素分組; 同樣字符分在同一組

1) if h[0] == "B" && a[0] == 1 then "false" 


2) h_size = h.size 

   a_size = a.size
  
   if h_size < a.size 

    分割元素

    |-> how to split?

   end

   if h_size == a.size 

      轉換序列

      |-> 先判斷'B'的位置是否能正確被轉換(h對應的index => a[index]==1)

      判斷是否轉換成功

      轉換失敗->判斷是否可重新切割調整->再次轉換序列並判斷是否成功->revursive

   end

   if h_size >a.size

      "false"

   end
>
1010 AAAAABBBBAAAA

[1,0,1,0] [A=>5,B=>4,A=>4]

[1,0,1,0] [A=>1,A=>4,B=>4,A=>4]


>
1100110 BBAABABBA

[1,1,0,0,1,1,0] [B=>2, A=>2, B=>1, A=>1, B=>2, A=>1]

step-1:

[1,1,0,0,1,1,0] [B=>2,A=>2,B=>1,A=>1,B=>2,A=>1]

分割元素 

origi: BB AA B A BB A

split: B B AA B A BB A

[1,1,0,0,1,1,0] [B＝>1,B=>1,A=>2,B=>1,A=>1,B=>2,A=>1]

     [1   , 1    , 0    , 0    , 1    , 1    , 0] 

     [B＝>1, B=>1  ,A=>2 , B=>1 , A=>1 , B=>2 , A=>1]

check T    , T     ,T    ,F     ==> break ==> 重新分割

step-2:

[1,1,0,0,1,1,0] [B=>2, A=>2, B=>1, A=>1, B=>2, A=>1]

分割元素 

origi: BB AA B A BB A

split: BB A A B A BB A

[1,1,0,0,1,1,0] [B＝>1,A=>1,A=>2,B=>1,A=>1,B=>2,A=>1]

...



->

1010 AAAAABBBBAAAABA

[1,0,1,0] [A=>5,B=>4,A=>4,B=>1,A=>1]

[1,0,1,0] [A=>1,A=>4,B=>4,A=>4]

- - -

