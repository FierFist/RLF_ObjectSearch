# 额外参数配置说明

## 配置结构

```json
{
    "nightTimeConfig": [20, 0, 6, 0],
    "enableBlockSearchAtNight": 0,
    "enableSaveCooldown": 1,
    "saveCooldownInMin": 10,
    "lightSourcesItemsList": [
        "Flashlight",
        "Roadflare",
        "Chemlight_ColorBase",
        "FlammableBase",
        "Headtorch_ColorBase",
        "TLRLight",
        "UniversalLight"
    ],
    "adminSteamID": []
}
```

---

## 参数说明

| 参数 | 类型 | 示例值 | 说明 |
|------|------|--------|------|
| **nightTimeConfig** | `Array [Integer]` | `[20, 0, 6, 0]` | 夜间时间配置：<br>• `20` = 夜晚开始小时（20:00）<br>• `0` = 夜晚开始分钟<br>• `6` = 夜晚结束小时（06:00）<br>• `0` = 夜晚结束分钟 |
| **enableBlockSearchAtNight** | `Integer (Boolean)` | `0` | 是否阻止玩家在夜间搜索物品：<br>• `1` = 启用（夜间禁止搜索）<br>• `0` = 禁用（夜间允许搜索） |
| **enableSaveCooldown** | `Integer (Boolean)` | `1` | 是否启用定时保存机制（服务器重启或间隔时间自动保存）：<br>• `1` = 启用<br>• `0` = 禁用 |
| **saveCooldownInMin** | `Integer` | `10` | 自动保存间隔（分钟） |
| **lightSourcesItemsList** | `Array [String]` | - | 视为“光源”的物品类名列表 |
| **adminSteamID** | `Array [String]` | `[]` | 可以在线更新配置的管理员 Steam ID 列表 |

---

## 光源物品

来自 `lightSourcesItemsList` 的物品会使玩家在夜晚（如果夜间搜索被禁用）仍然可以进行搜索。

---

## 配置示例

### 夜晚从 22:00 到 05:00

```json
"nightTimeConfig": [22, 0, 5, 0]
```

### 夜晚从 21:30 到 06:30

```json
"nightTimeConfig": [21, 30, 6, 30]
```

### 添加管理员

```json
"adminSteamID": [
    "76561198012345678",
    "76561198087654321"
]
```

---

## 说明

- 当 `enableBlockSearchAtNight = 1` 时，玩家只有在拥有列表中的有效光源时才能进行夜间搜索。  
- 保存冷却系统可避免数据过于频繁写入造成性能问题。  
- 时间使用 24 小时制。

