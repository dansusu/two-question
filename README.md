# two-question
1. 假设我们有 10 万条 URL 访问日志，如何按照访问次数给 URL 排序？  2. 有两个字符串数组，每个数组大约有 10 万条字符串，如何快速找出两个数组中相同的字符串？

python
1
import re
res = re.compile(r'\d+\.\d+\.\d+\.\d+')   # 匹配url
log = '''
192.168.0.26asasas,192.168.3.26asqwa,192.168.0.26asdasd'''  # 我们将要输入的内容，log中只是举例
results = res.findall(log)    # 查找所有匹配的
log_dic = {}
for result in results:  # 遍历
   if not log_dic.get(result):
      log_dic[result] = 1  
   else:
      sum = log_dic.get(str(result))
      sum+=1
      log_dic[result] = sum
sorted(log_dic, key=lambda x:x[0], reverse=False)   # 排序
print(log_dic)
2
# 例子
a_list = [
 "aaa","bbb","vvv"
]
b_list = [
    "aaa","bbb","ccc"
]
set1 = set(a_list).intersection(set(b_list))    # 使用set集合的合集
print(set1)
