# 如何编写带有版本的API

## 后端 API 框架

-   [moa-api](https://github.com/moajs/moa-api)

    一个基于node express快速开发api类后端的框架，适用于angularjs和ionic等
    前后端分离的项目

## RCSM分层思想

-   R = routes

    路由层，和express的一样，唯一不一样的是只要是在app/routes下面
    的js都会自动挂载到路由上。

-   C = controllers

    控制层，主要是负责接口处理结果如何返回，异常如何处理等逻辑控制，不处理具体逻辑
    
-   S = services

    业务逻辑层
    
-   M = models

    模型层
    
## 目录结构

    app/
    ├── controllers/
    ├── models/
    ├── services/
    └── routes/
        └── api/
            └── v0.1.1/
                ├── sends.js
                ├── receives.js
                ├── stock.js
                └── records.js
    
## 编写API接口
API 接口写在 routes/api 下，每个版本对应一个目录，如：v0.1.1

routes/api/sends.js : 

    var express = require('express');
    var router = express.Router();
    
    var $ = require('mount-controllers')(__dirname).send_controller;
    
    // 出库请求
    router.post('/show', $.api.show);
    
    // 拣货中
    router.get('/pick/:id', $.api.pick);
    
    // 拣货完成，填写物流信息
    router.get('/pick/:id/picked/', $.api.picked);
    
    // 确认发货提交
    router.post('/out', $.api.out);
    
    module.exports = router;
    
每个接口的 url ：

    http://127.0.0.1:3000/api/v0.1.1/sends/show
    
    http://127.0.0.1:3000/api/v0.1.1/sends/pick/:id
    
    http://127.0.0.1:3000/api/v0.1.1/sends/pick/:id/picked/
    
    http://127.0.0.1:3000/api/v0.1.1/sends/out

根据 RESTful 规范，是不建议将版本号写在 url 中的，然而，将版本号写在 url 可以增加
可读性等，并且更易于维护


## 编写API文档

<table cellspacing=0 cellpadding=10 >
    <tr>
        <td width=300px>
            <a href='sends/show.md'>sends/show</a>
        </td>
        <td width=600px>
            获取出库请求
        </td>
    </tr>
    <tr>
        <td>
            <a href='sends/pick_id.md'>sends/pick/:id</a>
        </td>
        <td>
            捡货中，获取该出库单的详细信息
        </td>
    </tr>
    <tr>
        <td>
            <a href='sends/pick_id_picked.md'>sends/pick/:id/picked/</a>
        </td>
        <td>
            拣货完成，填写物流单号、实际重量和费用
        </td>
    </tr>
    <tr>
        <td>
            <a href='sends/out.md'>sends/out</a>
        </td>
        <td>
            出库完成，更新数据库
        </td>
    </tr>
</table>
