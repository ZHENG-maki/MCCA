# MFAAvalonia 配套补丁

本项目的“下次执行时间”和可折叠多选清单需要 MFAAvalonia 提供界面与任务调度支持。为保持单仓库交付，配套源码改动保存在：

- `MFAAvalonia-v2.16.0-beta.3-custom.patch`

补丁基于 MFAAvalonia `v2.16.0-beta.3`（提交 `e345fcd`），包含：

- 任务级“下次执行时间”过滤与自动写入下周一；
- `TaskScheduleCompletionAction` 流水线完成信号；
- checkbox 选项的 `collapsible`、`expanded` 界面属性。

应用和构建：

```powershell
git clone https://github.com/MaaXYZ/MFAAvalonia.git
Set-Location MFAAvalonia
git checkout v2.16.0-beta.3
git am ..\MCCA\patches\MFAAvalonia-v2.16.0-beta.3-custom.patch
dotnet restore MFAAvalonia.Desktop\MFAAvalonia.Desktop.csproj -m:5
dotnet publish MFAAvalonia.Desktop\MFAAvalonia.Desktop.csproj -c Release -r win-x64 --no-restore -m:5
```
