# ElTreeSelect

## Props

<!-- @vuese:ElTreeSelect:props:start -->
|Name|Description|Type|Required|Default|
|---|---|---|---|---|
|value|v-model,存储的是treeParams.data里面的id|`String` / `Array`|`false`|`''`|
|styles|el-select样式|`Object`|`false`|{}|
|disabled|是否禁用文本框|`Boolean`|`false`|false|
|placement|弹出框位置|`String`|`false`|bottom|
|selectParams|文本框参数，几乎支持el-select所有的API<br>取消参数：<br>设定下拉框的弹出框隐藏：<br>`:popper-append-to-body="false"` <br>搜索从弹出框里面执行： <br>`:filterable="false"`|`Object`|`false`|Object默认参数：<br><br>是否可以清空选项：<br>`clearable: true,`<br><br>是否禁用：<br>`disabled: false,`<br><br>搜索框placeholder文字：<br>`placeholder: '请选择',`<br><br>是否多选：<br>`multiple: false`<br><br>|
|treeParams|下拉树参数，几乎支持el-tree所有的API<br>取消参数:<br>`:show-checkbox="selectParams.multiple"`<br>使用下拉框参数multiple判断是否对树进行多选<br>取消对el-tree的人为传参show-checkbox<br>`:node-key="propsValue"`     自动获取treeParams.props.value<br>`:draggable="false"`         屏蔽拖动|`Object`|`false`|Object默认参数：<br><br>在有子级的情况下是否点击父级关闭弹出框,false 只能点击子级关闭弹出框：`clickParent: false`<br><br>是否显示搜索框：<br>`filterable: false`<br><br>下拉树的数据：<br>`data:[]`<br><br>下拉树的props：<br>`props: {`<br>`children: 'children',`<br>`label: 'name',`<br>`value: 'flowId',`<br>`disabled: 'disabled'`<br>`}`|

<!-- @vuese:ElTreeSelect:props:end -->


## Events

<!-- @vuese:ElTreeSelect:events:start -->
|Event Name|Description|Parameters|
|---|---|---|
|searchFun|对外抛出搜索方法，自行判断是走后台查询，还是前端过滤<br>前端过滤：this.$refs.treeSelect.$refs.tree.filter(value);<br>后台查询：this.$refs.treeSelect.treeDataUpdateFun(data);|-|
|node-click|点击节点，对外抛出   `data, node, vm`<br>`data:` 当前点击的节点数据<br>`node:` 当前点击的node<br>`vm:` 当前组件的vm|-|
|check|点击复选框，对外抛出   `data, node, vm`<br>`data:` 当前点击的节点数据<br>`node:` 当前点击的node<br>`vm:` 当前组件的vm|-|
|input|下拉框清空，对外抛出``this.$emit('input', multiple ? [] : '');`|-|
|select-clear|下拉框清空，对外抛出``this.$emit('select-clear');`|-|

<!-- @vuese:ElTreeSelect:events:end -->


## Methods

<!-- @vuese:ElTreeSelect:methods:start -->
|Method|Description|Parameters|
|---|---|---|
|treeDataUpdateFun|树列表更新数据|Array|
|filterFun|本地过滤方法|String|

<!-- @vuese:ElTreeSelect:methods:end -->


