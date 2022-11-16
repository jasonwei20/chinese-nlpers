# chinese-nlpers

Output:
- Total unique authors in ACL 2022: 5,367
- Total unique Chinese authors in ACL 2022: 2,175
- Percent Chinese authors in ACL 2022: 40.5

Data from 
- https://aclanthology.org/events/acl-2022/
- https://chinese.yabla.com/chinese-pinyin-chart.php 

```python
all_names_list = set([x for x in all_names.split('\n') if len(x) > 3 and ' 'in x])
all_pinyin_list = set([x for x in all_pinyin.split('\n') if len(x) > 1])

num_chinese_people = 0
for name in all_names_list:
  last_name = name.split(' ')[-1]
  if last_name.lower() in all_pinyin_list:
    num_chinese_people += 1

percent_chinese_people = num_chinese_people / len(all_names_list) * 100
print(f'Total unique authors in ACL 2022: {len(all_names_list)}')
print(f'Total unique Chinese authors in ACL 2022: {num_chinese_people}')
print(f'Percent Chinese authors in ACL 2022: {percent_chinese_people:.1f}')
```
