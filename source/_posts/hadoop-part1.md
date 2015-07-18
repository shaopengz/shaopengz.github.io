title: "hadoop part1"
date: 2015-04-29 20:36:12
tags:
- big data
- hadoop
- java

---

## Phase of Hadoop process:

1. **Mapper**: read line by line, line number as key, line content as string value. Output tuple(K/V) by filter some things.
2. **Combiner**(Optional): invoker after mapper at Mapper Nodes, Hadoop not guarantee this process must happen or happens how many times.
3. **Partitioner**: According to the key value, distribute different Mapper output to different reducer nodes. The default behavior is by caculating the hash value of the key. But this can be rewrite if the distribution is not even.
4. **Reducer**: Collect multi outputs from different Mapper nodes and merge and process through reduce method.
