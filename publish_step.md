
# 发布步骤
* 在 https://www.npmjs.com/ 注册账号 
* 配置 registry
```
# 设置
npm config set registry https://registry.npmjs.org

# 查看
npm config get registry

# 查看所有配置
npm config list

```
* 登录账号
```
# 会提示输入账号、密码、邮箱验证码
npm login
```

* 发布
```
# 进入到自己项目根目录执行如下命令，等待发布成功
npm publish

```

# 注意事项
*  如果是命令行项目 `package.json` 的 `name` 的 `value` 和 `bin` 的 `key` 要保持一致
如下：package.json 示例
```
{
    "name": "hqcmd",
    "version": "1.0.0",
    "description": "",
    "main": "index.js",
    "author": "1710308677@qq.com",
    "license": "MIT",
    "repository": "https://github.com/HeHuiqi/HqCmd.git",
    "scripts": {
        "hello": "node index.js",
        "test": "echo \"Error: no test specified\" && exit 1"
    },
    "bin": {
        "hqcmd": "index.js"
    },
    "keywords": []
}
```
* 添加环境标识
如下：index.js 首行`#!/usr/bin/env node`
```
#!/usr/bin/env node
console.log("hello, hqcmd!");
```
* 重新发布要修改 `package.json` 中的 `versions` 保证不重复，否则会有如下错误
```
npm ERR! code E403
npm ERR! 403 403 Forbidden - PUT https://registry.npmjs.org/hqcmd - You cannot publish over the previously published versions: 1.0.0.

```
