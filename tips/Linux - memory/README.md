## memory


&nbsp;
&nbsp;

### 메모리확인

**free**

![](assets/markdown-img-paste-20180828155625755.png)

&nbsp;

### 캐시 제거

**echo 3 > /proc/sys/vm/drop_caches**

![](assets/markdown-img-paste-2018082815581751.png)

(options)

`echo 1 > /proc/sys/vm/drop_caches`  
: pagecache 비우기

`echo 2 > /proc/sys/vm/drop_caches`  
: dentries, inodes 비우기

`echo 3 > /proc/sys/vm/drop_caches`  
: pagecache, dentries, inodes 비우기

&nbsp;
&nbsp;
