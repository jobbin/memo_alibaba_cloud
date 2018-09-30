
[条件过滤](https://help.aliyun.com/document_detail/74416.html)
- 目前支持按照int_attr和str_attr两个字段进行过滤，分别表示整型字段和字符串类型字段。
- 新增图片时，用户可以指定上述任意一个字段值

[离线增量](https://help.aliyun.com/document_detail/66580.html)
- 增量内容写在increment.meta
  * cust_content是String，由用户自定义
```
{"operator":"ADD","item_id":"1000", "cat_id":0, "cust_content":"k1:v1,k2:v2,k3:v3", "pic_list":["girl_cloth1.jpg"]}
```
