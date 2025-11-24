# 搜索对象配置参数文档

## 参数表

| 参数 | 类型 | 说明 | 示例值 |
|------|------|------|--------|
| **主要参数** |
| `seasonPassIDConfig` | `string` | 赛季通行证配置 ID | `""` |
| `objectParamID` | `string` | 搜索对象参数的唯一 ID | `"RLF_Lootable_Hay"` |
| `buildingTypeParamIDHandle` | `object` | 针对建筑类型与特定掉落类型的参数处理器 | `{}` |
| **文本参数** |
| `objectTitle` | `string` | 对象显示标题（本地化键） | `"#STR_OS_Hay"` |
| `objectCustomIcon` | `string` | 自定义图标路径 | `""` |
| `actionText` | `string` | 交互动作文本（本地化键） | `"#STR_OS_SearchAction #STR_OS_Small_Hay"` |
| `actionUnlockText` | `string` | 使用工具打开时的动作文本（本地化键） | `"#STR_OS_OpenWithTool"` |
| `emptyText` | `string` | 当对象为空时显示的文本 | `""` |
| **音频参数** |
| `registeredSoundSet` | `string` | 搜索过程使用的音效组 ID | `"RLF_garbagesearching_SoundSet"` |
| **时间参数** |
| `coolDownAfterSearchInMin` | `number` | 搜索后的冷却时间（分钟） | `0` |
| `timeToSearch` | `number` | 搜索需要的时间（秒） | `3.0` |
| **伤害参数** |
| `chanceToDamageHands` | `number` | 手部受伤概率（0.0–1.0） | `0.0` |
| `damageToGloves` | `array[number]` | 对手套造成的伤害（fact 格式；若首项为 -1 则使用 min/max 随机） | `[0.0, 0.0, 0.0]` |
| `damageHandsFindedItemClassContains` | `array[string]` | 会在拾取时对手造成伤害的物品类名 | `[]` |
| **搜索限制** |
| `searchOnlyEmptyHands` | `number` | 是否只能空手搜索（0=否，1=是） | `0` |
| `enableIsKindOfItemInHands` | `number` | 是否启用“手中物品基类检测” | `0` |
| `ignoredObjectsInHands` | `array[string]` | 搜索时忽略的手中物品 | `[]` |
| **对象列表参数** |
| `objectsList` | `array[string]` | 可被搜索的对象类名列表 | `["farm_strawstack", "misc_haybale"]` |
| `ignoredObjectsList` | `array[string]` | 要忽略的对象类名列表 | `[]` |
| `uiWindowShowOffset` | `map[string, vector]` | 对象 UI 显示位置偏移（用于修复 UI 位置） | `[]` |
| **工具参数** |
| `enableIsKindOfForTool` | `number` | 是否检查工具基类（0=否，1=是） | `0` |
| `findWithToolMode` | `number` | 工具搜索模式：<br>• `1` = 必须用工具搜索<br>• `0` = 先用工具打开，再搜索 | `1` |
| `toolsToOpenList` | `array[string]` | 允许用于打开/搜索的工具类名 | `["Pitchfork"]` |
| `addHealthToToolAfterUse` | `array[number]` | 搜索后对工具耐久度变化（fact 格式；仅可正向） | `[0.0, 0.0, 0.0]` |
| `addQuantityToToolAfterUse` | `array[number]` | 搜索后对工具数量变化（fact 格式，可以正负） | `[0.0, 0.0, 0.0]` |
| **小游戏设置** |
| `showMiniGame` | `bool` | 是否启用小游戏（仅 findWithToolMode == 0 时有效） |  |
| `miniGameType` | `int` | 小游戏类型。0 = 撬锁 ，1 = 保险箱 <br><img width="100" alt="Screenshot_27" src="https://github.com/user-attachments/assets/bbfa1c51-c1d0-4d68-ae82-e2937b7c88a4" /><img width="100"  alt="Screenshot_26" src="https://github.com/user-attachments/assets/edc2ef3b-11cc-4caa-9c66-f6ee912ca6aa" /> |  |
| `miniGameToolsNeed` | `array[string]` | 触发小游戏所需工具列表；留空则无需工具 | `["Lockpick"]` |
| `miniGameSettings` | `array` | 小游戏设置数组：`lp_` 前缀为类型 0，`sg_` 为类型 1 | `[]` |
| `lp_RequiredHits` | `int` | 撬锁小游戏需命中次数 | `5` |
| `lp_RotationSpeed` | `float` | 指示器旋转速度（度/秒） | `180` |
| `lp_RandomRotation` | `bool` | 每次命中/失败后是否改变旋转方向 | `1` |
| `lp_TimeToOpen` | `float` | 打开所需时间 | `5.0` |
| `lp_TimePenalty` | `float` | 失败时的时间惩罚 | `1.0` |
| `lp_TimeBonus` | `float` | 成功时的时间奖励 | `1.0` |
| `lp_TargetTolerance` | `float` | 命中判定的角度容差（不低于 15°） | `15.0` |
| `sg_TotalCount` | `int` | 保险箱小游戏需猜测的值数量 | `3` |
| **区域参数** |
| `blockZones` | `array` | 禁止搜索的区域列表 | `[]` |
| `blockZonesRadius` | `array` | 禁区的半径列表 | `[]` |
| `tierZonesList` | `array` | 不同等级区域的覆盖设置 | `[]` |
| `chanceToTrapSpawn` | `float` | 在对象内生成陷阱的概率（0–1） | `[]` |
| `trapClassnameList` | `map` | 陷阱物品及概率列表（例如延迟引爆手雷） | `[]` |

---

## 配置示例

```json
{
    "seasonPassIDConfig": "",
    "objectParamID": "RLF_Lootable_PostBox",
    "buildingTypeParamIDHandle": {
        "HouseType": "objectParamID"
    },
    "objectTitle": "#STR_OS_PostBox",
    "objectCustomIcon": "relife_ObjectSearch/images/objects_icons/postal-box.edds",
    "actionText": "#STR_OS_SearchAction #STR_OS_Small_PostBox",
    "emptyText": "",
    "registeredSoundSet": "RLF_knigi_looting_SoundSet",
    "coolDownAfterSearchInMin": 0,
    "timeToSearch": 3.0,
    "chanceToDamageHands": 0.0,
    "damageToGloves": [
        0.0,
        4.0,
        8.0
    ],
    "damageHandsFindedItemClassContains": [],
    "searchOnlyEmptyHands": 0,
    "enableIsKindOfItemInHands": 0,
    "ignoredObjectsInHands": [],
    "showMiniGame": 0,
    "miniGameType": 0,
    "miniGameSettings": {
        "lp_RequiredHits": 0,
        "lp_RotationSpeed": 0.0,
        "lp_RandomRotation": 0,
        "lp_TimeToOpen": 0.0,
        "lp_TimePenalty": 0.0,
        "lp_TimeBonus": 0.0,
        "lp_TargetTolerance": 0.0,
        "sg_TotalCount": 0
    },
    "miniGameToolsNeed": [],
    "objectsList": [
        "RLF_Lootable_PostBox",
        "postbox1",
        "postbox2"
    ],
    "ignoredObjectsList": [],
    "uiWindowShowOffset": {
        "misc_postbox1.p3d": [
            1.0,
            -0.4,
            0.0
        ]
    },
    "selectionNeed": {},
    "enableIsKindOfForTool": 0,
    "disableRegisteredSoundSet": 0,
    "toolActionAnimHandler": {},
    "findWithToolMode": 0,
    "toolsToOpenList": [],
    "addHealthToToolAfterUse": [
        0.0,
        4.0,
        8.0
    ],
    "addQuantityToToolAfterUse": [
        0.0,
        4.0,
        8.0
    ],
    "blockZones": [],
    "blockZonesRadius": [],
    "chanceToTrapSpawn": 1.0,
    "trapClassnameList": {
        "RLF_RGD5Grenade_2Sec": 1.0
    },
    "tierZonesList": [
        {
            "tierName": "Tier1",
            "objectParamID": "CustomParamID",
            "buildingTypeParamIDHandle": {
                "HouseType": "paramID"
            },
            "zonesList": [
                [0.0, 0.0, 0.0]
            ],
            "zonesRadiusList": [
                0
            ]
        }
    ]
}
```

