# 自适应投机开启方式
omni_cli 配置文件中，D 侧设置 decode_gear_list 为略小于 max-num-seqs * (1 + num-speculative-tokens) 的值，例如 max-num-seqs=16, num-speculative-tokens=1, decode_gear_list 设为 24:
```yaml
args:
additional-config:
  graph_model_compile_config:
    decode_gear_list: [24]
```
在 speculative-config 里开启:
```
speculative-config: '{.....(保留 method, num_speculative, model 等配置), "enable_adaptive":true, "min_num_speculative_tokens":0}'
```
min_num_speculative_tokens 表示每个请求至少保留多少个投机 token，默认为 1，自适应投机对每个请求分配的投机 token 数在 [min_num_speculative_tokens, num_speculative_tokens] 范围内。
# 典型配置
1. 
```yaml
max-num-seqs: 16
num-speculative-tokens: 1
decode_gear_list: [24]
min_num_speculative_tokens: 0
```
2. 
```yaml
max-num-seqs: 24
num-speculative-tokens: 2
decode_gear_list: [64]
min_num_speculative_tokens: 1