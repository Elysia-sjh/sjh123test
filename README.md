UnknownDiagramError: No diagram type detected matching given configuration for text: ```mermaid
graph TD
    Start([开始]) --> Login[登录页面]
    Login --> Input[输入账号密码]
    Input --> Check{验证}
    
    Check -->|失败| Register[注册页面]
    Register --> RegInput[填写注册信息]
    RegInput --> CreateUser[创建用户]
    CreateUser --> Success[登录成功主页]
    
    Check -->|成功| Success

    System[(外卖平台系统)]
    Success --> Profile[个人信息维护]
    Profile -->|读写客户信息| System
    Success --> Address[地址管理]
    Address -->|读写地址信息| System
    Success --> Browse[店铺浏览/筛选/搜索]
    Browse -->|查询店铺/商品| System
    Browse --> ViewShop[查看店铺详情]
    ViewShop -->|查询商品详情| System
    ViewShop --> AddToCart[加入购物车]
    AddToCart -->|写入购物车| System
    Success --> Cart[查看购物车]
    Cart --> ViewCart[购物车详情]
    ViewCart --> ModifyCart[修改数量/删除]
    ModifyCart -->|更新购物车| System
    ModifyCart --> ChooseAddrTime[选择地址和送达时间]
    ChooseAddrTime -->|读取地址/生成订单| System
    ChooseAddrTime --> GenOrder[生成订单]
    GenOrder -->|创建订单| System
    GenOrder --> Pay[余额支付]
    Pay -->|更新订单状态| System
    Pay --> OrderDone[订单完成]
    Success --> EvalEntry[评价/投诉入口]
    EvalEntry --> SelectOrder[选择订单]
    OrderDone --> SelectOrder
    SelectOrder -->|查询订单| System
    SelectOrder --> ChooseAction{选择操作}
    ChooseAction -->|评价| SubmitEval[提交评价]
    ChooseAction -->|投诉| SubmitComplaint[提交投诉]
    SubmitEval -->|写入评价信息| System
    SubmitComplaint -->|写入投诉信息| System
    Success --> AI[小墨AI推荐]
    AI --> RequestRec[请求推荐]
    RequestRec -->|获取推荐数据| System
    RequestRec --> ShowRec[显示推荐结果]
    AddToCart --> Cart
