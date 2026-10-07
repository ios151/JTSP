# 加藤视频 重写脚本

加藤视频 VIP 解锁 + 付费视频解锁 + 去广告。Surge / Loon / Stash / Quantumult X / Shadowrocket / Egern 通用。

---

## 订阅地址

**Surge / Egern**

https://raw.githubusercontent.com/ios151/JTSP/refs/heads/main/modules/katovideo.sgmodule

**Quantumult X**

https://raw.githubusercontent.com/ios151/JTSP/refs/heads/main/modules/katovideo.conf

**Loon**

https://raw.githubusercontent.com/ios151/JTSP/refs/heads/main/modules/katovideo.lpx

> Stash / Shadowrocket 等：用 [Script-Hub](https://github.com/Script-Hub-Org/Script-Hub) 把 `.sgmodule` 转换后订阅，或直接用 `modules/katovideo.shadowrocket.sgmodule`。

---

<details>
<summary><b>功能</b></summary>

- VIP 解锁、会员有效期 / 昵称
- 去广告（开屏 / banner / 弹窗 / 浮窗 / 游戏入口 / 抽奖）
- 付费 / 试看视频解锁，试看流→完整流
- 漫画（anime）付费章节解锁：解锁付费章节、去价格标签，付费未购章节自动回填图片内容（用持久化键 `jtsp_anime_cache` 缓存章节图片）
- 只需选日志级别，其余（去广告 / 解锁VIP / 解锁视频 / 去游戏）默认开启

</details>

<details>
<summary><b>加解密</b></summary>

请求/响应体为 `{"encrypt":"<hex>"}`，算法 **AES-128-CBC-PKCS7**。32 字节 secretKey 拆分：前 16 = key，后 16 = IV。

key/IV 由服务端 RSA 握手下发，脚本启动时从 Worker 获取，写入持久化键 `jtsp_key`（含 `expireAt`），未过期不重复拉取；取不到时回退内置值。

</details>

<details>
<summary><b>主机（需自行更新）</b></summary>

❗ API 主机随机轮换且变化快（随机子域名 + 顶级域 + 非标准端口）。若拒解密/不生效，多半是主机变了——**请自行把拓包拿到的最新主机/顶级域加进各模块的 `hostname`**（MITM 不区分端口）。

当前已内置线路：
```
txxncjt.7vvfzx7.my:34218
xy8scio.8oy75gk.xyz:13001
akhyb7k.iyquagu.xyz:38017
8non608.k58z3gl.my:13001
lym6vq1.dmwvoky.fit:38017
```

</details>
