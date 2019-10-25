---
title: JWT要点
date: 2019-10-16 23:43:14
type: "jwt"
---

### 使用建议

* 不要存放敏感信息在Token里。
* Payload中的exp时效不要设定太长。
* 开启Only Http预防XSS攻击。
* 如果担心重播攻击（replay attacks ）可以增加jti（JWT ID），exp（有效时间） Claim。
* 在你的应用程序应用层中增加黑名单机制，必要的时候可以进行Block做阻挡（这是针对掉令牌被第三方使用窃取的手动防御）。
