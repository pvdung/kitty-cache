Super simple local in memory cache using java.util.concurrent package for high performance thread-safe design.

It's only 75 lines of code including comments and getters. [View code](http://code.google.com/p/kitty-cache/source/browse/trunk/src/com/spaceprogram/kittycache/KittyCache.java)

## Features ##

  * Super simple using only a few constructs from java.util.concurrent package
  * Supports maximum cache size
  * Supports item expiration

## Getting Started ##

Very easy:
```
// Create a new cache
KittyCache cache = new KittyCache(5000); // 5000 is max number of objects
// Put an object into the cache
cache.put("mykey", value, 500); // 500 is time to live in seconds
// Get an object from the cache
value = cache.get("mykey");
```

## Performance ##

I've only tested again Ehcache, but here's 3 separate runs, each with max cache size of 10,000 elements and all in memory. All values in ms. (see source for actual test code).

#### Performance Run 1 ####

Test 10,000 Puts
ehcache=44
kitty=40

Test 100,000 Puts
ehcache=652
kitty=159

Test 1,000,000 Puts
ehcache=6701
kitty=1594

Test 100 Thread Concurrency and 1,000,000 Puts
ehcache=310385
kittycache=97210

#### Performance Run 2 ####

Test 10,000 Puts
ehcache=47
kitty=39

Test 100,000 Puts
ehcache=681
kitty=116

Test 1,000,000 Puts
ehcache=6593
kitty=1213

Test 100 Thread Concurrency and 1,000,000 Puts
ehcache=294903
kittycache=92105

#### Performance Run 3 ####

Test 10,000 Puts
ehcache=73
kitty=57

Test 100,000 Puts
ehcache=730
kitty=115

Test 1,000,000 Puts
ehcache=7028
kitty=1002

Test 100 Thread Concurrency and 1,000,000 Puts
ehcache=304804
kittycache=92594

## What's with the name? ##

I know, the name is lame. I was just thinking of something tiny and fast and kitty cat came to mind and.... I don't even like cats. ;) Kidding, they are cute... sometimes.