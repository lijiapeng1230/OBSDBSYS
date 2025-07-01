# 节目导视系统配置文件说明

## 配置文件路径
`./config.json`
##
自动翻页面板

使用键盘 ctrl+shift+E 打开
## 配置参数说明

### 基础设置
| 字段名                 | 类型   | 示例值                              | 说明                                                                 |
|-----------------------|--------|-------------------------------------|----------------------------------------------------------------------|
| `system_title`        | string | `"今日节目导视"`                   | 系统主标题，显示在页面顶部                                         |
| `system_subtitle`     | string | `"破天星辰网络直播频道"`           | 系统副标题，显示在主标题下方                                       |
| `system_copyright`    | string | `"© 2025 节目导视系统 - 内部技术版"` | 版权信息，显示在技术控制面板                                       |
| `page_duration_seconds` | number | `5`                                | 每页节目停留时间（秒）                                             |
| `playback_loop_mode`  | string | `"stop"`                           | 播放模式：`"stop"`-停在最后一页，`"cycle"`-循环播放                 |

### 字体设置
| 字段名           | 类型   | 示例值                  | 说明                             |
|------------------|--------|-------------------------|----------------------------------|
| `font_settings.family` | string | `"'Microsoft YaHei', sans-serif"` | 系统字体（支持CSS字体族语法）    |
| `font_settings.weight` | string | `"600"`                 | 字体粗细（100-900）              |
| `font_settings.letter_spacing` | string | `"1.5px"`            | 字符间距                         |
| `font_settings.title_size` | string | `"2.2rem"`          | 节目标题字体大小                 |

### 边框样式
| 字段名                     | 类型   | 示例值                 | 说明                     |
|----------------------------|--------|------------------------|--------------------------|
| `border_styles.item_border` | string | `"2px solid #00dbde"` | 每个节目条目的边框样式   |
| `border_styles.container_border` | string | `"3px solid #fc00ff"` | 整个节目列表容器的边框样式 |

### 节目时间表
| 字段名         | 类型  | 说明                 |
|----------------|-------|----------------------|
| `program_schedule` | array | 节目列表数组         |
| `program_name` | string | 节目名称（必需）     |
| `air_time`     | string | 播出时间（HH:MM格式）|

## 配置示例
```json
{
  "system_title": "今日节目导视",
  "system_subtitle": "破天星辰网络直播频道",
  "system_copyright": "© 2025 节目导视系统 - 内部技术版",
  "page_duration_seconds": 5,
  "playback_loop_mode": "stop",
  "font_settings": {
    "family": "'Microsoft YaHei', sans-serif",
    "weight": "600",
    "letter_spacing": "1.5px",
    "title_size": "2.2rem"
  },
  "border_styles": {
    "item_border": "2px solid #00dbde",
    "container_border": "3px solid #fc00ff"
  },
  "program_schedule": [
    {"program_name": "晨间新闻直播", "air_time": "07:00"},
    {"program_name": "财经早报", "air_time": "08:30"},
    // ...其他节目
  ]
}
```

## 注意事项
1. 修改配置文件后需刷新页面生效
2. 所有字段名称均为小写字母和下划线组合
3. 节目时间使用24小时制（HH:MM）