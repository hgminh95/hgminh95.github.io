---
layout: post
title:  "Backtracking"
date:   2015-07-29
parent: "cl-2016"
tag:
- algorithm
- cl
comments: true
---

## Tài liệu tham khảo

http://lequydonhadong.edu.vn/Images/Library/TTQUAYLUI.pdf

https://commons.wikimedia.org/wiki/File:Sudoku_solved_by_bactracking.gif

## Code

Bài toán n-hậu - [ideone](http://ideone.com/MYIvAe)

{% highlight pascal %}
const MAXN : integer = 20;
var
    r           : array[1..20] of boolean;
    d1          : array[-20..20] of boolean;
    d2          : array[2..2 * 20] of boolean;
    res         : longint;
    n           : integer;

procedure attempt(step: integer);
var i: integer;
begin
    if (step > n) then
    begin
        res:= res + 1;
        exit();
    end;

    for i:= 1 to n do
    begin
        if r[i] or d1[i - step] or d2[i + step] then continue;

        r[i]:= true;
        d1[i - step]:= true;
        d2[i + step]:= true;

        attempt(step + 1);

        r[i]:= false;
        d1[i - step]:= false;
        d2[i + step]:= false;
    end;
end;

begin
    readln(n);

    attempt(1);

    writeln(res);
end.
{% endhighlight %}

Liệt kê các hoán vị của n phần tử - [ideone](http://ideone.com/twHj1M)

{% highlight pascal %}
var
    n           : integer;
    a           : array[1..10] of integer;
    trace       : array[1..10] of boolean;

procedure print_perm();
var i: integer;
begin
    for i:= 1 to n do write(a[i], ' ');
    writeln;
end;

procedure attempt(step: integer);
var i: integer;
begin
    if (step > n) then
    begin
        print_perm();
        exit();
    end;

    for i:= 1 to n do
    begin
        if trace[i] then continue;

        trace[i]:= true;
        a[step]:= i;

        attempt(step + 1);

        trace[i]:= false;
    end;
end;

begin
    readln(n);

    attempt(1);
end.
{% endhighlight %}
