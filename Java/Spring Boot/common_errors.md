# COMMON ERRORS

## 1. Lỗi eclips bị treo mỗi khi chạy server
- Đọc file log của project đó để biết chi tiết về lỗi (file .log được đặt trong workspace/.metadata/.log)

### 1.1. Unbind Command.
```
!ENTRY org.eclipse.jface 2 0 2023-07-16 09:14:27.443
!MESSAGE Keybinding conflicts occurred.  They may interfere with normal accelerator operation.
!SUBENTRY 1 org.eclipse.jface 2 0 2023-07-16 09:14:27.443
!MESSAGE A conflict occurred for CTRL+SHIFT+T:
Binding(CTRL+SHIFT+T,
	ParameterizedCommand(Command(org.eclipse.jdt.ui.navigate.open.type,Open Type,
		Open a type in a Java editor,
		Category(org.eclipse.ui.category.navigate,Navigate,null,true),
		WorkbenchHandlerServiceHandler("org.eclipse.jdt.ui.navigate.open.type"),
		,,true),null),
	org.eclipse.ui.defaultAcceleratorConfiguration,
	org.eclipse.ui.contexts.window,,,system)
Binding(CTRL+SHIFT+T,
	ParameterizedCommand(Command(org.eclipse.lsp4e.symbolinworkspace,Go to Symbol in Workspace,
		,
		Category(org.eclipse.lsp4e.category,Language Servers,null,true),
		WorkbenchHandlerServiceHandler("org.eclipse.lsp4e.symbolinworkspace"),
		,,true),null),
	org.eclipse.ui.defaultAcceleratorConfiguration,
	org.eclipse.ui.contexts.window,,,system)
```
Hãy chú ý các từ sau:
- Keybinding conflicts occurred
- CTRL+SHIFT+T
- Open Type
- Go to Symbol in Workspace

Cách fix lỗi này là mở phần mềm `Eclipse -> Window -> Preferences -> General -> Keys`, tìm Command có tên là `Open Type` và `Go to Symbol in Workspace` với When là `In Windows`, chọn command này và nhấn nút `Unbind Command`

### 1.2. Start Eclipse -clean
- Tắt Eclipse nếu phần mềm đang được mở
- Mở thư mục chứa Eclipse.exe
- Tạo file `.bat` với nội dung
```
@echo off
start eclipse -clean
exit
```
Chạy file .bat này để mở eclipse (không mở bằng file Eclipse.exe)

### 1.3. Delete folder .metadata
- Tắt Eclipse nếu phần mềm đang được mở
- Mở thư mục chứa workspace
- Xóa thư mục `.metadata`
- Mở lại Eclipse để kiểm tra lỗi còn xuất hiện không

### 1.4. Switch workspace
- Tắt Eclipse nếu phần mềm đang được mở
- Tạo thư mục mới làm workspace
- Mở Eclipse chọn workspace mới này
- Tạo project mới và copy các file code cần thiết từ project cũ qua
- (hoặc switch workspace cũ)
- Kiểm tra lỗi còn xuất hiện hay không