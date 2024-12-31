# Sofast Tauri Api Use Example

如快插件使用 Tauri API 示例。

## 使用

1. 导入相关依赖（似乎放开发依赖就行？），注意是 Tauri2 的 API，有些 API 没开放权限，如果需要用到，可以找我开一下：
    ```json
    {
      "devDependencies": {
        "@tauri-apps/api": "2.0.2",
        "@tauri-apps/plugin-notification": "2.0.0"
      }
    }
    ```
1. 使用 API：
    ```typescript
    getCurrentWebviewWindow().hide()
    ```
