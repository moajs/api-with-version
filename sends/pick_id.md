### sends/pick/:id

捡货中，获取该出库单的详细信息

### URL

`http://10.1.1.229:3000/api/v0.1.1/sends/pick/:id`

### 支持格式

JSON

### HTTP请求方式

GET

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
            id
        </td>
        <td>
            是
        </td>
        <td>
            String
        </td>
        <td>
            要查询的出库单号
        </td>
    </tr>
</table>

### 返回结果示例

    {
        data: {
            order_id: "S000010119",
            to_name: "大白",
            to_phone: "13800138000",
            to_address: "福建省-莆田市-城厢区-打鼓南路",
            express: "百世汇通",
            total_count: 32,
            created_at_date: "2015-09-07",
            created_at_time: "15:18",
            products: [
                {
                    name: "牛奶",
                    count: 22
                },
                {
                    name: "红牛",
                    count: 10
                }
            ]
        },
        status: {
            code: 0,
            msg: "request success!"
        }
    }