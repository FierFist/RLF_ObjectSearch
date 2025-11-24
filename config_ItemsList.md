# 物品配置说明

## 用途说明

该配置用于存储所有物品的数据，并在后续通过物品 ID 进行使用。

---

## 物品配置结构

```json
{
    "itemID": 9999,
    "itemRarity": "",
    "itemIsLiquid": 1,
    "liquidMlCount": [
        -1.0,
        500.0,
        900.0
    ],
    "liquidMaxCount": 1000,
    "liquidTypeID": 512,
    "className": "",
    "itemHealth": [
        -1.0,
        0.4000000059604645,
        1.0
    ],
    "isStackable": 0,
    "itemQuantity": [
        -1.0,
        0.10000000149011612,
        0.20000000298023225
    ],
    "itemLiquidType": 0
}
```

---

## 参数说明

| 参数 | 类型 | 示例值 | 说明 |
|------|------|--------|------|
| **itemID** | `Integer` | `1001` | 游戏中物品的唯一识别 ID |
| **itemRarity** | `String (Hex)` | `0x75FFAB00` | 物品稀有度颜色（RGBA Hex）。0x75 是透明度，一般不要改。 |
| **itemIsLiquid** | `bool` | `false` | 是否为液体（而不是普通物品）。 |
| **liquidTypeID** | `int` | `512` | 液体类型 ID。 |
| **itemLiquidType** | `int` | `0` | 物品可填充液体的类型 ID。 |
| **className** | `String` | `AKM` | 物品类名。 |
| **itemHealth** | `Array [Float]` | `[-1, 0.4, 1]` | 物品耐久值范围：<br>• `-1` = 固定数值，如果为 -1 则随机<br>• `0.4` = 随机最小值<br>• `1` = 随机最大值 |
| **isStackable** | `Integer (Boolean)` | `1` | 是否可堆叠：<br>• `1` = 可堆叠<br>• `0` = 不可堆叠 |
| **itemQuantity** | `Array [Float]` | `[-1, 0.1, 1]` | 物品数量范围：<br>• `-1` = 固定数值，如果为 -1 则随机<br>• `0.1` = 随机最小值<br>• `1` = 随机最大值<br>注：弹匣或子弹为实际数量，不是百分比 |
| **liquidMlCount** | `Array [Float]` | `[-1, 500, 900]` | 液体数量范围（仅 itemIsLiquid = 1 时有效）：<br>• `-1` = 固定数值，如果为 -1 则随机<br>• `500` = 随机最小值<br>• `900` = 随机最大值 |
| **liquidMaxCount** | `float` | `1000` | 液体最大容量（用于进度条显示）。 |

---

## 说明

- `itemHealth` 与 `itemQuantity` 使用三段式结构，用于设置随机范围或固定数值。
- 稀有度字段使用带 Alpha 通道的 Hex 颜色值。

