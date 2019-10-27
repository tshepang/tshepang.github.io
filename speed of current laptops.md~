+++
title = "speed of current laptops"
date = 2019-10-27

[taxonomies]
tags = ["hardware", "Rust"]
+++

I decided to get me my dream laptop, a Lenovo X1 Carbon (code 20KGS3X910).
It has amazing keyboard (as promised) as well as amazing touchpad.
The performance is sad though, less than my work laptop,
an Asus UX410 (itself a replacement of [the UX305] whose battery circuitry got fried).

To check performance, I used [Rust JSON Benchmark]:

```
git clone https://github.com/serde-rs/json-benchmark
cd json-benchmark
git checkout 1d4986c2083c8f164f86116f19d70dd32b7519bf
rustup default 1.38.0
cargo run --release --bin json-benchmark
```

Results for the X1 Carbon:

```
                                DOM                  STRUCT
======= serde_json ======= parse|stringify ===== parse|stringify ====
data/canada.json         140 MB/s   310 MB/s   390 MB/s   230 MB/s
data/citm_catalog.json   240 MB/s   400 MB/s   560 MB/s   520 MB/s
data/twitter.json        170 MB/s   530 MB/s   360 MB/s   520 MB/s

======= json-rust ======== parse|stringify ===== parse|stringify ====
data/canada.json         250 MB/s   600 MB/s
data/citm_catalog.json   340 MB/s   510 MB/s
data/twitter.json        290 MB/s   600 MB/s

==== rustc_serialize ===== parse|stringify ===== parse|stringify ====
data/canada.json          94 MB/s    40 MB/s    69 MB/s    29 MB/s
data/citm_catalog.json   100 MB/s   120 MB/s    76 MB/s   140 MB/s
data/twitter.json         59 MB/s   240 MB/s    47 MB/s   260 MB/s

======= simd-json ======== parse|stringify ===== parse|stringify ====
data/canada.json         240 MB/s   310 MB/s   400 MB/s
data/citm_catalog.json   610 MB/s   430 MB/s   900 MB/s
data/twitter.json        470 MB/s   510 MB/s   620 MB/s
```

Results for the UX305:

```
                                DOM                  STRUCT
======= serde_json ======= parse|stringify ===== parse|stringify ====
data/canada.json         240 MB/s   510 MB/s   570 MB/s   390 MB/s
data/citm_catalog.json   370 MB/s   680 MB/s   920 MB/s   890 MB/s
data/twitter.json        290 MB/s   900 MB/s   640 MB/s   920 MB/s

======= json-rust ======== parse|stringify ===== parse|stringify ====
data/canada.json         500 MB/s   990 MB/s
data/citm_catalog.json   700 MB/s   860 MB/s
data/twitter.json        520 MB/s  1030 MB/s

==== rustc_serialize ===== parse|stringify ===== parse|stringify ====
data/canada.json         160 MB/s    65 MB/s   120 MB/s    51 MB/s
data/citm_catalog.json   170 MB/s   210 MB/s   120 MB/s   240 MB/s
data/twitter.json        100 MB/s   410 MB/s    80 MB/s   440 MB/s

======= simd-json ======== parse|stringify ===== parse|stringify ====
data/canada.json         380 MB/s   490 MB/s   650 MB/s
data/citm_catalog.json  1000 MB/s   790 MB/s  1540 MB/s
data/twitter.json        870 MB/s   900 MB/s  1030 MB/s
```

[Rust JSON Benchmark]: https://github.com/serde-rs/json-benchmark
[the UX305]: http://tshepang.net/asus-zenbook-ux305fa
