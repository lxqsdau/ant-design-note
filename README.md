# ant-design-note
* form 初始值 initialValue
  有initialValue字段，Select的placeholder不显示
* setFieldsValue 改变表单值，不要用value
* Modal confirmLoading 为true时，点击事件不响应


# dva
1. Dva action 发起路由跳转  this.props.dispatch(routerRedux.push('/contract/waiting_sign'));
  dispatch属性需要connect获取
2. This.props.dispatch后，并不会在下面立刻获得值，在render可打印出信息