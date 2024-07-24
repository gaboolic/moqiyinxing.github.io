# 模糊音、飞键



你使用的方案.shema.yaml 里自带了一些飞键，可选择性开启、关闭

<pre><code>speller:
  algebra:
<strong>    ## 飞键 可选择性开启
</strong>    - derive/^([y])j/$1f/
    - derive/^qx/qw/
    - derive/^xq/xo/
    - derive/^qq/qo/
    - derive/^ww/wi/
    # - derive/^y([a-df-qs-z])/e$1/ # y -> e互击
    - derive/^j([a-twyz])/f$1/ # j -> f互击
    # - derive/^jn/jv/
    # - derive/^mn/mv/
    # - derive/^jm/jz/
    - derive/^([y])h/$1g/
    # - derive/^([rgv])f/$1m/
    - derive/^([rgv])c/$1n/
</code></pre>

模糊音同理，也是使用derive把平舌音翘舌音互转、前后鼻音互转

```
speller:
  algebra:
    ## 模糊音 可选择性开启
    - derive/^z([a-z])/v$1/
    - derive/^c([a-z])/i$1/
    - derive/^s([a-z])/u$1/
    - derive/^v([a-z])/z$1/
    - derive/^i([a-z])/c$1/
    - derive/^u([a-z])/s$1/
```
