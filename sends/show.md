### sends/show

获取出库请求

### URL

`http://10.1.1.229:3000/api/v0.1.1/sends/show`

### 支持格式

JSON

### HTTP请求方式

POST

### 请求参数

<table cellspacing=0 cellpadding=10 >
    <tr>
        <th>
            参数
        </th>
        <th>
            必选
        </th>
        <th>
            类型及范围
        </th>
        <th>
            说明
        </th>
    </tr>
    <tr>
        <td>
            lastId
        </td>
        <td>
            是
        </td>
        <td>
            mongoose.Types.ObjectId
        </td>
        <td>
            用于分页，如果不存在则视为第一页
        </td>
    </tr>
</table>

### 返回结果示例

    {
        data: {
            items: [
                {
                    username: "懒羊羊",
                    order_id: "S000010119",
                    total_count: 32,
                    created_at: "今天15:18",
                    status: "待处理",
                    img: "http://mengxiaoban.cn/images/express_logo/huitongkuaidi.jpg"
                }
            ],
            lastId: "55ed3a512e32c9270dad66f0"
        },
        status: {
            code: 0,
            msg: "request success!"
        }
    }