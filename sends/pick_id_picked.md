### sends/pick/:id/picked/

拣货完成，获取物流公司名称

### URL

`http://10.1.1.229:3000/api/v0.1.1/sends/pick/:id/picked/`

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
            express: "百世汇通"
        },
        status: {
            code: 0,
            msg: "request success!"
        }
    }