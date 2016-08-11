---
layout: post
title:  "Basic Data Structure"
date:   2015-07-29
parent: "cl-2016"
tag:
- algorithm
- cl
comments: true
---

## Stack

https://www.cs.usfca.edu/~galles/visualization/StackArray.html

{% highlight pascal %}
var a: array[1..STACK_MAX_SIZE] of longint;
    rear: longint;

procedure init();
begin
    rear:= 0;
end;

function pop(): longint;
begin
    rear:= rear - 1;
    exit(a[rear + 1]);
end;

function top(): longint;
begin
    exit(a[rear]);
end;

function push(int u): longint;
begin
    rear:= rear + 1;
    a[rear]:= u;
end;

{% endhighlight %}

## Queue

https://www.cs.usfca.edu/~galles/visualization/QueueArray.html

{% highlight pascal %}
var q: array[0..QUEUE_MAX_SIZE] of longint;
    front, rear: longint;

procedure init();
begin
    front:= 0;
    rear:= -1;
end;

function top():longint;
begin
    exit(a[front]);
end;

function pop():longint;
begin
    rear:= rear - 1;
    exit(q[rear + 1]);
end;

procedure push(u: longint);
begin
    rear:= rear + 1;
    q[rear]:= u;
end;

{% endhighlight %}
