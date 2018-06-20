# ant-design-note
* form 初始值 initialValue
  有initialValue字段，Select的placeholder不显示
* setFieldsValue 改变表单值，不要用value
* Modal confirmLoading 为true时，点击事件不响应


# dva
1. Dva action 发起路由跳转  this.props.dispatch(routerRedux.push('/contract/waiting_sign'));
  dispatch属性需要connect获取
2. This.props.dispatch后，并不会在下面立刻获得值，在render可打印出信息
3. 跟路由不变，查询参数改变
  /worker/profile?userId=0 --> /worker/profile?userId=1
  不使用props获取数据，因为在componentWillReceiveProps触发action，会进入死循环
  用state保存数据
  componentWillReceiveProps(nextProps) {
    console.log('componentWillReceiveProps')
    const { history } = this.props;
    const urlSearch = history.location.search;
    const userId = urlSearch.split('&')[0].split('=')[1];
    this.dispatchFeatch(userId);
  }