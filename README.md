# use

我的 Cursor 使用配置备份。

## 内容

| 文件 | 说明 |
| --- | --- |
| [`settings.json`](./settings.json) | Cursor 用户设置（来自 `~/Library/Application Support/Cursor/User/settings.json`） |
| [`extensions.json`](./extensions.json) | 已安装插件列表（含版本号） |

## 恢复方式

### 设置

将 `settings.json` 复制到 Cursor 用户配置目录：

```bash
# macOS
cp settings.json "$HOME/Library/Application Support/Cursor/User/settings.json"
```

### 插件

批量安装 `extensions.json` 中的所有插件：

```bash
jq -r '.extensions[].id' extensions.json | xargs -L1 cursor --install-extension
```

> 如 `cursor` 命令不在 PATH 中，macOS 下可使用
> `/Applications/Cursor.app/Contents/Resources/app/bin/cursor`。

## 更新备份

```bash
cp "$HOME/Library/Application Support/Cursor/User/settings.json" settings.json
cursor --list-extensions --show-versions   # 手动同步到 extensions.json
```
