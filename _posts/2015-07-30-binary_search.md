---
layout: post
title:  "Binary Search"
date:   2015-07-30
parent: "cl-2016"
tag:
- algorithm
- cl
comments: true
---

## Tài liệu tham khảo

https://blog.penjee.com/binary-vs-linear-search-animated-gifs/

## Code

Tìm kiếm phần tử trong dãy đã sắp xếp tăng dần có giá trị bằng số k cho trưóc

{% highlight pascal %}
function binary_search(k: longint): longint;
var l, r: longint;
    mid: longint;
begin
    l:= 1;
    r:= n;

    while (l <= r) do
        begin
            mid:= (l + r) div 2;

            if (a[mid] = k) then exit(mid);

            if (a[mid] > k) then r:= mid - 1
            else l:= mid + 1;
        end;

    exit(-1);
end;

binary_search(k);

{% endhighlight %}

Tìm kiếm phần tử trong dãy đã sắp xếp có giá trị không lớn hơn số k cho trước

{% highlight pascal %}

function binary_search(k: longint): longint;
var l, r: longint;
    mid: longint;
begin
    l:= 1;
    r:= n;
    res:= -1;

    while (l < r) do
        begin
            mid:= (l + r) div 2;

            if (a[mid] > k) then r:= mid - 1
            else begin
                l:= mid + 1;
                res:= mid;
            end;
        end;

    exit(res);
end;

binary_search(k);

{% endhighlight %}

Tìm nghiệm của phương trình f(x) = 0 trong [a, b] với f(x) là hàm liên tục
và có đúng 1 nghiệm trong [a, b]

{% highlight pascal %}
function f(x: double): double;
begin
    // Trả về gía trị của f(x)
end;

function solve(double a, double b): double;
var eps, mid: double;
begin
    eps:= 0.000001;

    while (abs(a - b) > eps) do
        begin
            mid = (a + b) / 2;

            if (f(a) * f(mid) > 0) then a:= mid;
            else b:= mid;
        end;

    return (a + b) / 2;
end;

solve(4, 5);

{% endhighlight %}
