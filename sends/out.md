### sends/out

出库完成，更新数据库

### URL

`http://10.1.1.229:3000/api/v0.1.1/sends/out`

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
            order_id
        </td>
        <td>
            是
        </td>
        <td>
            String
        </td>
        <td>
            出库单号
        </td>
    </tr>
    <tr>
        <td>
            delivery_number
        </td>
        <td>
            是
        </td>
        <td>
            String
        </td>
        <td>
            快递单号
        </td>
    </tr>
    <tr>
        <td>
            weight
        </td>
        <td>
            是
        </td>
        <td>
            Number
        </td>
        <td>
            实际重量(kg)
        </td>
    </tr>
    <tr>
        <td>
            price
        </td>
        <td>
            是
        </td>
        <td>
            Number
        </td>
        <td>
            实际费用(元)
        </td>
    </tr>
</table>

### 请求数据示例

    {
        order_id: "S000010119",
        delivery_number: "KD100101001",
        weight: "12",
        price: "100"
    }