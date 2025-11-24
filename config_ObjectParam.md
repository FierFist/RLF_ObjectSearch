# 可搜刮物体（Lootable Object）配置说明

## 配置结构

```json
{
    "RLF_Lootable_Fridge": {
        "chanceToSuccess": 0.11,
        "itemListPreset": ["ExamplePreset1"],
        "perksHandlesParam": [
            {
                "perkID": 10,
                "chanceToSuccess": 0.11,
                "chanceToCount": {
                    "1": 1.0
                },
                "listOfItemsID": {
                    "287": 1.0
                }
            }
        ],
        "chanceToCount": {
            "1": 1.0
        },
        "listOfItemsID": {
            "287": 1.0,
            "288": 1.0,
            "289": 1.0
        }
    }
}
```

---

## 主要参数说明

| 参数 | 类型 | 示例值 | 说明 |
|------|------|--------|------|
| **对象键（ClassName）** | `String` | `RLF_Lootable_Fridge` | 可搜刮物体的配置 ID |
| **chanceToSuccess** | `Float` | `0.11` | 基础成功搜索概率（11%） |
| **itemListPreset** | `Array [String]` | `["ExamplePreset1"]` | 使用的物品预设列表 |

---

## perksHandlesParam 结构说明（需要安装模组 relife_AdvSkills）

该部分用于设置 **技能（Perks）对搜刮物体的影响**。

| 参数 | 类型 | 说明 |
|------|------|------|
| **perkID** | `Integer` | 技能的唯一 ID |
| **chanceToSuccess** | `Float` | 玩家拥有此技能时的成功率（同样为 11%） |
| **chanceToCount** | `Object {String: Float}` | 不同数量的物品掉落几率 |
| **listOfItemsID** | `Object {String: Float}` | 该技能对应的物品掉落 ID 及权重 |

---

### perksHandlesParam 示例

| 字段 | 值 | 说明 |
|------|------|------|
| `perkID` | `10` | 影响搜刮结果的技能 ID |
| `chanceToSuccess` | `0.11` | 拥有技能后的搜索成功率 |
| `chanceToCount` → `"1"` | `1.0` | 100% 掉落 1 个物品 |
| `listOfItemsID` → `"287"` | `1.0` | 指定物品 ID 的掉落权重 |

---

## 基础掉落参数

| 参数 | 类型 | 说明 |
|------|------|------|
| **chanceToCount** | `Object {String: Float}` | 每种数量的掉落概率 |
| **listOfItemsID** | `Object {String: Float}` | 掉落物列表，键为物品 ID，值为掉落权重 |

---

### chanceToCount 格式示例

```json
{
    "1": 1.0,    
    "2": 0.5,    
    "3": 0.25    
}
```

- `"1": 1.0` → 100% 掉落 1 个  
- `"2": 0.5` → 50% 掉落 2 个  
- `"3": 0.25` → 25% 掉落 3 个  

---

### listOfItemsID 格式示例

```json
{
    "287": 1.0,
    "288": 1.0,
    "289": 1.0
}
```

---

## 掉落权重逻辑

权重越高，掉落概率越大。

| Item ID | 权重 | 掉落概率 |
|---------|------|----------|
| 287 | 1.0 | 33.3% |
| 288 | 1.0 | 33.3% |
| 289 | 1.0 | 33.3% |

**公式：**

```
概率 = 单个物品权重 / 所有权重总和
```

---

## 不同权重示例

```json
"listOfItemsID": {
    "287": 2.0,   // 50%
    "288": 1.0,   // 25%
    "289": 1.0    // 25%
}
```

---

## 说明

- `chanceToSuccess` 决定是否能成功找到物品  
- `perksHandlesParam` 用于为拥有技能的玩家提供特殊掉落  
- `itemListPreset` 可调用外部预设物品列表  
- 所有概率中的 `1.0` 表示 100%  

