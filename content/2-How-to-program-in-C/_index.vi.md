+++
title = "Lập trình bằng ngôn ngữ C" 
weight = 2
chapter = false
pre = " <b> 2. </b> "
+++

#### Cấu hình VS Code cho Microsoft C++

Trong hướng dẫn này, bạn sẽ cấu hình Visual Studio Code để sử dụng trình biên dịch và gỡ lỗi Microsoft Visual C++ trên Windows.

Sau khi cấu hình VS Code, bạn sẽ biên dịch và gỡ lỗi một chương trình Hello World đơn giản trong VS Code. Hướng dẫn này không dạy chi tiết về bộ công cụ Microsoft C++ hay ngôn ngữ C++. Với những chủ đề đó, có rất nhiều tài liệu tốt trên mạng.

Nếu bạn gặp bất kỳ vấn đề nào, hãy thoải mái tạo issue cho hướng dẫn này trong [kho lưu trữ tài liệu VS Code](https://github.com/microsoft/vscode-docs/issues).

#### Yêu cầu trước khi bắt đầu

Để hoàn thành thành công hướng dẫn này, bạn cần:

1. Cài đặt [Visual Studio Code](/download)

2. Cài đặt [tiện ích mở rộng C/C++ cho VS Code](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools). Bạn có thể cài đặt tiện ích C/C++ bằng cách tìm kiếm 'c++' trong mục Extensions (`kb(workbench.view.extensions)`).

![CS](https://raw.githubusercontent.com/baobaoupcloud/cs-1/main/static/images/0002/0001.png?featherlight=false&width=90pc)

3. Cài đặt bộ công cụ trình biên dịch Microsoft Visual C++ (MSVC).

   Nếu bạn có phiên bản Visual Studio mới, hãy mở Visual Studio Installer từ menu Start của Windows và kiểm tra xem workload C++ đã được chọn chưa. Nếu chưa cài đặt, hãy đánh dấu vào ô và chọn nút **Modify** trong trình cài đặt.

   Bạn cũng có thể cài đặt workload **Desktop development with C++** mà không cần cài đặt đầy đủ IDE Visual Studio. Từ trang [Downloads](https://visualstudio.microsoft.com/downloads/#remote-tools-for-visual-studio-2022) của Visual Studio, cuộn xuống cho đến khi thấy **Tools for Visual Studio** trong phần **All Downloads** và chọn tải về **Build Tools for Visual Studio 2022**.

![CS](https://raw.githubusercontent.com/baobaoupcloud/cs-1/main/static/images/0002/0002.png?featherlight=false&width=90pc)

   Điều này sẽ khởi chạy Visual Studio Installer, hiển thị hộp thoại các workload có sẵn của Visual Studio Build Tools. Đánh dấu workload **Desktop development with C++** và chọn **Install**.

![CS](https://raw.githubusercontent.com/baobaoupcloud/cs-1/main/static/images/0002/0003.png?featherlight=false&width=90pc)

>**Lưu ý**: Bạn có thể sử dụng bộ công cụ C++ từ Visual Studio Build Tools cùng với Visual Studio Code để biên dịch, build và xác minh bất kỳ codebase C++ nào miễn là bạn có giấy phép Visual Studio hợp lệ (Community, Pro hoặc Enterprise) mà bạn đang sử dụng để phát triển codebase C++ đó.

#### Kiểm tra cài đặt Microsoft Visual C++ 

Để sử dụng MSVC từ dòng lệnh hoặc VS Code, bạn phải chạy từ **Developer Command Prompt for Visual Studio**. Một shell thông thường như PowerShell, Bash hoặc Windows command prompt không có các biến môi trường path cần thiết.

Để mở Developer Command Prompt for VS, bắt đầu gõ 'developer' trong menu Start của Windows, và bạn sẽ thấy nó xuất hiện trong danh sách gợi ý. Tên chính xác phụ thuộc vào phiên bản Visual Studio hoặc Visual Studio Build Tools bạn đã cài đặt. Chọn mục này để mở command prompt.

![CS](https://raw.githubusercontent.com/baobaoupcloud/cs-1/main/static/images/0002/0004.png?featherlight=false&width=90pc)

Bạn có thể kiểm tra xem trình biên dịch C++, `cl.exe`, đã được cài đặt đúng chưa bằng cách gõ 'cl' và bạn sẽ thấy thông báo bản quyền với phiên bản và mô tả sử dụng cơ bản.

![CS](https://raw.githubusercontent.com/baobaoupcloud/cs-1/main/static/images/0002/0005.png?featherlight=false&width=90pc)

Nếu Developer Command Prompt đang sử dụng thư mục BuildTools làm thư mục khởi đầu (bạn không nên đặt dự án ở đó), hãy điều hướng đến thư mục người dùng của bạn (`C:\users\{tên người dùng}\`) trước khi bắt đầu tạo dự án mới.


>**Lưu ý**: Nếu vì lý do nào đó bạn không thể chạy VS Code từ **Developer Command Prompt**, bạn có thể tìm giải pháp thay thế để build các dự án C++ với VS Code trong phần [Chạy VS Code bên ngoài Developer Command Prompt](#run-vs-code-outside-the-developer-command-prompt).

#### Tạo Hello World

Từ Developer Command Prompt, tạo một thư mục trống có tên "projects" nơi bạn có thể lưu trữ tất cả các dự án VS Code, sau đó tạo một thư mục con có tên "helloworld", điều hướng vào nó và mở VS Code (`code`) trong thư mục đó (`.`) bằng cách nhập các lệnh sau:

```bat
mkdir projects
cd projects
mkdir helloworld
cd helloworld
code .
```

Lệnh "code ." mở VS Code trong thư mục làm việc hiện tại, thư mục này trở thành "workspace" của bạn. Khi bạn làm theo hướng dẫn, bạn sẽ thấy ba tệp được tạo trong thư mục `.vscode` trong workspace:

- `tasks.json` (hướng dẫn build)
- `launch.json` (cài đặt trình gỡ lỗi)
- `c_cpp_properties.json` (đường dẫn trình biên dịch và cài đặt IntelliSense)

#### Thêm tệp mã nguồn

Trong thanh tiêu đề File Explorer, chọn nút **New File** và đặt tên tệp là `helloworld.cpp`.

![CS](https://raw.githubusercontent.com/baobaoupcloud/cs-1/main/static/images/0002/0006.png?featherlight=false&width=90pc)

#### Thêm mã nguồn hello world

Bây giờ dán mã nguồn này vào:

```cpp
#include <iostream>
#include <vector>
#include <string>

using namespace std;

int main()
{
    vector<string> msg {"Hello", "C++", "World", "from", "VS Code", "and the C++ extension!"};

    for (const string& word : msg)
    {
        cout << word << " ";
    }
    cout << endl;
}
```

Nhấn `kb(workbench.action.files.save)` để lưu tệp. Chú ý cách tệp bạn vừa thêm xuất hiện trong chế độ xem **File Explorer** (`kb(workbench.view.explorer)`) ở thanh bên của VS Code:

![CS](https://raw.githubusercontent.com/baobaoupcloud/cs-1/main/static/images/0002/0007.png?featherlight=false&width=90pc)

Bạn cũng có thể bật [Auto Save](/docs/editor/codebasics.md#save-auto-save) để tự động lưu các thay đổi tệp của bạn, bằng cách chọn **Auto Save** trong menu chính **File**.

Activity Bar ở bên trái xa cho phép bạn mở các chế độ xem khác nhau như **Search**, **Source Control** và **Run**. Bạn sẽ xem chế độ xem **Run** sau trong hướng dẫn này. Bạn có thể tìm hiểu thêm về các chế độ xem khác trong [tài liệu Giao diện người dùng VS Code](/docs/getstarted/userinterface.md).

>**Lưu ý**: Khi bạn lưu hoặc mở tệp C++, bạn có thể thấy thông báo từ tiện ích mở rộng C/C++ về việc có sẵn phiên bản Insiders, cho phép bạn thử các tính năng và bản sửa lỗi mới. Bạn có thể bỏ qua thông báo này bằng cách chọn `X` (**Clear Notification**).

#### Khám phá IntelliSense

Trong tệp `helloworld.cpp` mới của bạn, di chuột qua `vector` hoặc `string` để xem thông tin kiểu. Sau khi khai báo biến `msg`, bắt đầu gõ `msg.` như khi bạn gọi một hàm thành viên. Bạn sẽ ngay lập tức thấy danh sách hoàn thành hiển thị tất cả các hàm thành viên và một cửa sổ hiển thị thông tin kiểu cho đối tượng `msg`:

![CS](https://raw.githubusercontent.com/baobaoupcloud/cs-1/main/static/images/0002/0008.png?featherlight=false&width=90pc)

Bạn có thể nhấn phím `kbstyle(Tab)` để chèn thành viên được chọn; sau đó, khi bạn thêm dấu ngoặc đơn mở, bạn sẽ thấy thông tin về bất kỳ đối số nào mà hàm yêu cầu.

Tôi sẽ tiếp tục dịch phần tiếp theo:

#### Chạy helloworld.cpp

Hãy nhớ rằng, tiện ích mở rộng C++ sử dụng trình biên dịch C++ đã được cài đặt trên máy của bạn để build chương trình. Đảm bảo bạn đã cài đặt trình biên dịch C++ trước khi thử chạy và gỡ lỗi `helloworld.cpp` trong VS Code.

1. Mở `helloworld.cpp` để nó là tệp đang hoạt động.
2. Nhấn nút play ở góc trên bên phải của trình soạn thảo.

![CS](https://raw.githubusercontent.com/baobaoupcloud/cs-1/main/static/images/0002/0009.png?featherlight=false&width=90pc)

3. Chọn **C/C++: cl.exe build and debug active file** từ danh sách trình biên dịch được phát hiện trên hệ thống của bạn.

![CS](https://raw.githubusercontent.com/baobaoupcloud/cs-1/main/static/images/0002/00010.png?featherlight=false&width=90pc)

Bạn sẽ chỉ được yêu cầu chọn trình biên dịch lần đầu tiên chạy `helloworld.cpp`. Trình biên dịch này sẽ được đặt làm trình biên dịch "mặc định" trong tệp `tasks.json`.

4. Sau khi build thành công, đầu ra của chương trình sẽ xuất hiện trong **Terminal** tích hợp.

![CS](https://raw.githubusercontent.com/baobaoupcloud/cs-1/main/static/images/0002/00011.png?featherlight=false&width=90pc)

Nếu bạn gặp lỗi khi cố gắng build và gỡ lỗi với cl.exe, hãy đảm bảo bạn đã [khởi động VS Code từ Developer Command Prompt for Visual Studio](#check-your-microsoft-visual-c-installation) sử dụng lệnh tắt `code .`.

![CS](https://raw.githubusercontent.com/baobaoupcloud/cs-1/main/static/images/0002/00012.png?featherlight=false&width=90pc)

Lần đầu tiên bạn chạy chương trình, tiện ích mở rộng C++ tạo `tasks.json`, bạn sẽ tìm thấy nó trong thư mục `.vscode` của dự án. `tasks.json` lưu trữ cấu hình build.

Tệp `tasks.json` mới của bạn phải trông tương tự như JSON dưới đây:

```json
{
"version": "2.0.0",
"tasks": [
    {
        "type": "shell",
        "label": "C/C++: cl.exe build active file",
        "command": "cl.exe",
        "args": [
            "/Zi",
            "/EHsc",
            "/Fe:",
            "${fileDirname}\\${fileBasenameNoExtension}.exe",
            "${file}"
        ],
        "problemMatcher": [
            "$msCompile"
        ],
        "group": {
            "kind": "build",
            "isDefault": true
        },
        "detail": "Task generated by Debugger."
    }
]
}
```

>**Lưu ý**: Bạn có thể tìm hiểu thêm về các biến `tasks.json` trong [tài liệu tham khảo biến](/docs/editor/variables-reference.md).

Cài đặt `command` chỉ định chương trình để chạy; trong trường hợp này là "cl.exe". Mảng `args` chỉ định các đối số dòng lệnh sẽ được truyền cho cl.exe. Các đối số này phải được chỉ định theo thứ tự mà trình biên dịch mong đợi.

Task này yêu cầu trình biên dịch C++ lấy tệp đang hoạt động (`${file}`), biên dịch nó và tạo một tệp thực thi (`/Fe:` switch) trong thư mục hiện tại (`${fileDirname}`) với cùng tên như tệp đang hoạt động nhưng với phần mở rộng `.exe` (`${fileBasenameNoExtension}.exe`), kết quả là `helloworld.exe` cho ví dụ của chúng ta.

#### Chạy helloworld.cpp

Hãy nhớ rằng, tiện ích mở rộng C++ sử dụng trình biên dịch C++ đã được cài đặt trên máy của bạn để build chương trình. Đảm bảo bạn đã cài đặt trình biên dịch C++ trước khi thử chạy và gỡ lỗi `helloworld.cpp` trong VS Code.

1. Mở `helloworld.cpp` để nó là tệp đang hoạt động.
2. Nhấn nút play ở góc trên bên phải của trình soạn thảo.

![CS](https://raw.githubusercontent.com/baobaoupcloud/cs-1/main/static/images/0002/0009.png?featherlight=false&width=90pc)

3. Chọn **C/C++: cl.exe build and debug active file** từ danh sách trình biên dịch được phát hiện trên hệ thống của bạn.

![CS](https://raw.githubusercontent.com/baobaoupcloud/cs-1/main/static/images/0002/00010.png?featherlight=false&width=90pc)

Bạn sẽ chỉ được yêu cầu chọn trình biên dịch lần đầu tiên chạy `helloworld.cpp`. Trình biên dịch này sẽ được đặt làm trình biên dịch "mặc định" trong tệp `tasks.json`.

4. Sau khi build thành công, đầu ra của chương trình sẽ xuất hiện trong **Terminal** tích hợp.

![CS](https://raw.githubusercontent.com/baobaoupcloud/cs-1/main/static/images/0002/00011.png?featherlight=false&width=90pc)

Nếu bạn gặp lỗi khi cố gắng build và gỡ lỗi với cl.exe, hãy đảm bảo bạn đã [khởi động VS Code từ Developer Command Prompt for Visual Studio](#check-your-microsoft-visual-c-installation) sử dụng lệnh tắt `code .`.

![CS](https://raw.githubusercontent.com/baobaoupcloud/cs-1/main/static/images/0002/00012.png?featherlight=false&width=90pc)

Lần đầu tiên bạn chạy chương trình, tiện ích mở rộng C++ tạo `tasks.json`, bạn sẽ tìm thấy nó trong thư mục `.vscode` của dự án. `tasks.json` lưu trữ cấu hình build.

Tệp `tasks.json` mới của bạn phải trông tương tự như JSON dưới đây:

```json
{
"version": "2.0.0",
"tasks": [
    {
        "type": "shell",
        "label": "C/C++: cl.exe build active file",
        "command": "cl.exe",
        "args": [
            "/Zi",
            "/EHsc",
            "/Fe:",
            "${fileDirname}\\${fileBasenameNoExtension}.exe",
            "${file}"
        ],
        "problemMatcher": [
            "$msCompile"
        ],
        "group": {
            "kind": "build",
            "isDefault": true
        },
        "detail": "Task generated by Debugger."
    }
]
}
```

>**Lưu ý**: Bạn có thể tìm hiểu thêm về các biến `tasks.json` trong [tài liệu tham khảo biến](/docs/editor/variables-reference.md).

Cài đặt `command` chỉ định chương trình để chạy; trong trường hợp này là "cl.exe". Mảng `args` chỉ định các đối số dòng lệnh sẽ được truyền cho cl.exe. Các đối số này phải được chỉ định theo thứ tự mà trình biên dịch mong đợi.

Task này yêu cầu trình biên dịch C++ lấy tệp đang hoạt động (`${file}`), biên dịch nó và tạo một tệp thực thi (`/Fe:` switch) trong thư mục hiện tại (`${fileDirname}`) với cùng tên như tệp đang hoạt động nhưng với phần mở rộng `.exe` (`${fileBasenameNoExtension}.exe`), kết quả là `helloworld.exe` cho ví dụ của chúng ta.

Giá trị `label` là những gì bạn sẽ thấy trong danh sách task; bạn có thể đặt tên này theo ý muốn.

Giá trị `detail` là những gì bạn sẽ thấy như mô tả của task trong danh sách task. Rất nên đổi tên giá trị này để phân biệt nó với các task tương tự.

Giá trị `problemMatcher` chọn trình phân tích cú pháp đầu ra để tìm lỗi và cảnh báo trong đầu ra của trình biên dịch. Đối với cl.exe, bạn sẽ nhận được kết quả tốt nhất nếu sử dụng problem matcher `$msCompile`.

Từ giờ trở đi, nút play sẽ đọc từ `tasks.json` để biết cách build và chạy chương trình của bạn. Bạn có thể định nghĩa nhiều task build trong `tasks.json`, và task nào được đánh dấu là mặc định sẽ được nút play sử dụng. Trong trường hợp bạn cần thay đổi trình biên dịch mặc định, bạn có thể chạy **Tasks: Configure default build task**. Hoặc bạn có thể sửa đổi tệp `tasks.json` và xóa mặc định bằng cách thay thế đoạn này:

```json
    "group": {
        "kind": "build",
        "isDefault": true
    },
```

bằng:

```json
    "group": "build",
```

#### Sửa đổi tasks.json

Bạn có thể sửa đổi `tasks.json` để build nhiều tệp C++ bằng cách sử dụng đối số như `"${workspaceFolder}/*.cpp"` thay vì `"${file}"`. Điều này sẽ build tất cả các tệp `.cpp` trong thư mục hiện tại của bạn. Bạn cũng có thể sửa đổi tên tệp đầu ra bằng cách thay thế `"${fileDirname}\\${fileBasenameNoExtension}.exe"` bằng tên tệp cố định (ví dụ: `"${workspaceFolder}\\myProgram.exe"`).

#### Gỡ lỗi helloworld.cpp

Để gỡ lỗi code của bạn:

1. Quay lại `helloworld.cpp` để nó là tệp đang hoạt động.
2. Đặt điểm dừng bằng cách nhấp vào lề trình soạn thảo hoặc sử dụng F9 trên dòng hiện tại.
![CS](https://raw.githubusercontent.com/baobaoupcloud/cs-1/main/static/images/0002/00013.png?featherlight=false&width=90pc)
3. Từ drop-down bên cạnh nút play, chọn **Debug C/C++ File**.
![CS](https://raw.githubusercontent.com/baobaoupcloud/cs-1/main/static/images/0002/00014.png?featherlight=false&width=90pc)
4. Chọn **C/C++: cl.exe build and debug active file** từ danh sách trình biên dịch được phát hiện trên hệ thống của bạn (bạn sẽ chỉ được yêu cầu chọn trình biên dịch lần đầu tiên chạy hoặc gỡ lỗi `helloworld.cpp`).
![CS](https://raw.githubusercontent.com/baobaoupcloud/cs-1/main/static/images/0002/00015.png?featherlight=false&width=90pc)

Nút play có hai chế độ: **Run C/C++ File** và **Debug C/C++ File**. Nó sẽ mặc định về chế độ được sử dụng lần cuối. Nếu bạn thấy biểu tượng gỡ lỗi trong nút play, bạn có thể chọn nút play để gỡ lỗi thay vì chọn mục trong menu drop-down.

Nếu bạn gặp lỗi khi cố gắng build và gỡ lỗi với cl.exe, hãy đảm bảo bạn đã [khởi động VS Code từ Developer Command Prompt for Visual Studio](#check-your-microsoft-visual-c-installation) sử dụng lệnh tắt `code .`.

![CS](https://raw.githubusercontent.com/baobaoupcloud/cs-1/main/static/images/0002/00016.png?featherlight=false&width=90pc)

#### Khám phá trình gỡ lỗi

Trước khi bắt đầu thực hiện từng bước trong code, hãy dành một chút thời gian để nhận thấy một số thay đổi trong giao diện người dùng:

- Terminal tích hợp xuất hiện ở dưới cùng của trình soạn thảo mã nguồn. Trong tab **Debug Output**, bạn thấy đầu ra cho biết trình gỡ lỗi đang hoạt động.
- Trình soạn thảo làm nổi bật dòng nơi bạn đặt điểm dừng trước khi bắt đầu trình gỡ lỗi:

![CS](https://raw.githubusercontent.com/baobaoupcloud/cs-1/main/static/images/0002/00017.png?featherlight=false&width=90pc)

- Chế độ xem **Run and Debug** ở bên trái hiển thị thông tin gỡ lỗi. Bạn sẽ thấy một ví dụ sau trong hướng dẫn.

- Ở đầu trình soạn thảo code, bảng điều khiển gỡ lỗi xuất hiện. Bạn có thể di chuyển nó xung quanh màn hình bằng cách kéo các chấm ở bên trái.

![CS](https://raw.githubusercontent.com/baobaoupcloud/cs-1/main/static/images/0002/00018.png?featherlight=false&width=90pc)

#### Thực hiện từng bước trong code

Bây giờ bạn đã sẵn sàng để bắt đầu thực hiện từng bước trong code.

1. Nhấp hoặc nhấn biểu tượng **Step over** trong bảng điều khiển gỡ lỗi.

![CS](https://raw.githubusercontent.com/baobaoupcloud/cs-1/main/static/images/0002/00019.png?featherlight=false&width=90pc)

   Điều này sẽ chuyển thực thi chương trình đến dòng đầu tiên của vòng lặp for, và bỏ qua tất cả các lệnh gọi hàm nội bộ trong các lớp `vector` và `string` được gọi khi biến `msg` được tạo và khởi tạo. Chú ý sự thay đổi trong cửa sổ **Variables** ở bên trái.

![CS](https://raw.githubusercontent.com/baobaoupcloud/cs-1/main/static/images/0002/00020.png?featherlight=false&width=90pc)

   Trong trường hợp này, các lỗi là dự kiến vì, mặc dù tên biến cho vòng lặp hiện đã hiển thị với trình gỡ lỗi, câu lệnh vẫn chưa thực thi, vì vậy không có gì để đọc tại thời điểm này. Tuy nhiên, nội dung của `msg` hiển thị vì câu lệnh đó đã hoàn thành.

1. Nhấn **Step over** một lần nữa để chuyển đến câu lệnh tiếp theo trong chương trình này (bỏ qua tất cả code bên trong được thực thi để khởi tạo vòng lặp). Bây giờ, cửa sổ **Variables** hiển thị thông tin về các biến vòng lặp.

2. Nhấn **Step over** một lần nữa để thực thi câu lệnh `cout`. (Lưu ý rằng tiện ích mở rộng C++ không in bất kỳ đầu ra nào vào **Debug Console** cho đến khi vòng lặp kết thúc.)

3. Nếu muốn, bạn có thể tiếp tục nhấn **Step over** cho đến khi tất cả các từ trong vector được in ra console. Nhưng nếu bạn tò mò, hãy thử nhấn nút **Step Into** để thực hiện từng bước qua mã nguồn trong thư viện chuẩn C++!

![CS](https://raw.githubusercontent.com/baobaoupcloud/cs-1/main/static/images/0002/00021.png?featherlight=false&width=90pc)

   Để quay lại code của bạn, một cách là tiếp tục nhấn **Step over**. Một cách khác là đặt điểm dừng trong code của bạn bằng cách chuyển sang tab `helloworld.cpp` trong trình soạn thảo code, đặt con trỏ chèn vào câu lệnh `cout` bên trong vòng lặp và nhấn `kb(editor.debug.action.toggleBreakpoint)`. Một chấm đỏ xuất hiện trong máng bên trái để chỉ ra rằng một điểm dừng đã được đặt trên dòng này.

![CS](https://raw.githubusercontent.com/baobaoupcloud/cs-1/main/static/images/0002/00022.png?featherlight=false&width=90pc)

   Sau đó nhấn `kb(workbench.action.debug.start)` để bắt đầu thực thi từ dòng hiện tại trong header thư viện chuẩn. Thực thi sẽ dừng tại `cout`. Nếu muốn, bạn có thể nhấn `kb(editor.debug.action.toggleBreakpoint)` một lần nữa để tắt điểm dừng.

#### Thiết lập theo dõi

Đôi khi bạn có thể muốn theo dõi giá trị của một biến khi chương trình của bạn thực thi. Bạn có thể làm điều này bằng cách thiết lập một **watch** trên biến.

1. Đặt con trỏ chèn bên trong vòng lặp. Trong cửa sổ **Watch**, chọn dấu cộng và trong hộp văn bản, gõ `word`, là tên của biến vòng lặp. Bây giờ xem cửa sổ Watch khi bạn thực hiện từng bước qua vòng lặp.

![CS](https://raw.githubusercontent.com/baobaoupcloud/cs-1/main/static/images/0002/00023.png?featherlight=false&width=90pc)

2. Thêm một watch khác bằng cách thêm câu lệnh này trước vòng lặp: `int i = 0;`. Sau đó, bên trong vòng lặp, thêm câu lệnh: `++i;`. Bây giờ thêm một watch cho `i` như bạn đã làm trong bước trước.

3. Để nhanh chóng xem giá trị của bất kỳ biến nào trong khi thực thi đang tạm dừng tại điểm dừng, bạn có thể di chuột qua nó.

![CS](https://raw.githubusercontent.com/baobaoupcloud/cs-1/main/static/images/0002/00024.png?featherlight=false&width=90pc)

#### Tùy chỉnh gỡ lỗi với launch.json

Khi bạn gỡ lỗi với nút play hoặc `kb(workbench.action.debug.start)`, tiện ích mở rộng C++ tạo một cấu hình gỡ lỗi động ngay lập tức.

Có những trường hợp bạn muốn tùy chỉnh cấu hình gỡ lỗi của mình, chẳng hạn như chỉ định các đối số để truyền cho chương trình trong thời gian chạy. Bạn có thể định nghĩa các cấu hình gỡ lỗi tùy chỉnh trong tệp `launch.json`.

Để tạo `launch.json`, chọn **Add Debug Configuration** từ menu drop-down của nút play.

![CS](https://raw.githubusercontent.com/baobaoupcloud/cs-1/main/static/images/0002/00025.png?featherlight=false&width=90pc)

Sau đó bạn sẽ thấy một dropdown cho các cấu hình gỡ lỗi được xác định trước khác nhau. Chọn **C/C++: cl.exe build and debug active file**.

![CS](https://raw.githubusercontent.com/baobaoupcloud/cs-1/main/static/images/0002/00026.png?featherlight=false&width=90pc)

VS Code tạo một tệp `launch.json`, trông giống như thế này:

```json
{
"version": "0.2.0",
"configurations": [
    {
        "name": "C/C++: cl.exe build and debug active file",
        "type": "cppvsdbg",
        "request": "launch",
        "program": "${fileDirname}\\${fileBasenameNoExtension}.exe",
        "args": [],
        "stopAtEntry": false,
        "cwd": "${workspaceFolder}",
        "environment": [],
        "externalConsole": false,
        "preLaunchTask": "C/C++: cl.exe build active file"
    }
]
}
```

Trong JSON trên, `program` chỉ định chương trình bạn muốn gỡ lỗi. Ở đây nó được đặt thành thư mục tệp đang hoạt động (`${fileDirname}`) và tên tệp đang hoạt động với phần mở rộng `.exe` (`${fileBasenameNoExtension}.exe`), nếu `helloworld.cpp` là tệp đang hoạt động thì sẽ là `helloworld.exe`. Thuộc tính `args` là một mảng các đối số để truyền cho chương trình trong thời gian chạy.

Theo mặc định, tiện ích mở rộng C++ sẽ không thêm bất kỳ điểm dừng nào vào mã nguồn của bạn và giá trị `stopAtEntry` được đặt thành `false`.

Thay đổi giá trị `stopAtEntry` thành `true` để khiến trình gỡ lỗi dừng tại phương thức `main` khi bạn bắt đầu gỡ lỗi.

> Từ giờ trở đi, nút play và `kb(workbench.action.debug.start)` sẽ đọc từ tệp `launch.json` của bạn khi khởi chạy chương trình để gỡ lỗi.

#### Cấu hình C/C++

Nếu bạn muốn kiểm soát nhiều hơn đối với tiện ích mở rộng C++, bạn có thể tạo một tệp `c_cpp_properties.json`, cho phép bạn thay đổi các cài đặt như đường dẫn đến trình biên dịch, đường dẫn include, tiêu chuẩn C++ (mặc định là C++17), và nhiều hơn nữa.

Bạn có thể xem giao diện cấu hình C/C++ bằng cách chạy lệnh **C/C++: Edit Configurations (UI)** từ Command Palette (`kb(workbench.action.showCommands)`).

![CS](https://raw.githubusercontent.com/baobaoupcloud/cs-1/main/static/images/0002/00027.png?featherlight=false&width=90pc)

Thao tác này mở trang **C/C++ Configurations**. Khi bạn thực hiện thay đổi ở đây, VS Code sẽ ghi chúng vào một tệp có tên `c_cpp_properties.json` trong thư mục `.vscode`.

![CS](https://raw.githubusercontent.com/baobaoupcloud/cs-1/main/static/images/0002/00028.png?featherlight=false&width=90pc)

Trong JSON trên, `program` chỉ định chương trình bạn muốn gỡ lỗi. Ở đây nó được đặt thành thư mục tệp đang hoạt động (`${fileDirname}`) và tên tệp đang hoạt động với phần mở rộng `.exe` (`${fileBasenameNoExtension}.exe`), nếu `helloworld.cpp` là tệp đang hoạt động thì sẽ là `helloworld.exe`. Thuộc tính `args` là một mảng các đối số để truyền cho chương trình trong thời gian chạy.

Theo mặc định, tiện ích mở rộng C++ sẽ không thêm bất kỳ điểm dừng nào vào mã nguồn của bạn và giá trị `stopAtEntry` được đặt thành `false`.

Thay đổi giá trị `stopAtEntry` thành `true` để khiến trình gỡ lỗi dừng tại phương thức `main` khi bạn bắt đầu gỡ lỗi.

> Từ giờ trở đi, nút play và `kb(workbench.action.debug.start)` sẽ đọc từ tệp `launch.json` của bạn khi khởi chạy chương trình để gỡ lỗi.

#### Cấu hình C/C++

Nếu bạn muốn kiểm soát nhiều hơn đối với tiện ích mở rộng C++, bạn có thể tạo một tệp `c_cpp_properties.json`, cho phép bạn thay đổi các cài đặt như đường dẫn đến trình biên dịch, đường dẫn include, tiêu chuẩn C++ (mặc định là C++17), và nhiều hơn nữa.

Bạn có thể xem giao diện cấu hình C/C++ bằng cách chạy lệnh **C/C++: Edit Configurations (UI)** từ Command Palette (`kb(workbench.action.showCommands)`).

![CS](https://raw.githubusercontent.com/baobaoupcloud/cs-1/main/static/images/0002/00027.png?featherlight=false&width=90pc)

Thao tác này mở trang **C/C++ Configurations**. Khi bạn thực hiện thay đổi ở đây, VS Code sẽ ghi chúng vào một tệp có tên `c_cpp_properties.json` trong thư mục `.vscode`.

![CS](https://raw.githubusercontent.com/baobaoupcloud/cs-1/main/static/images/0002/00028.png?featherlight=false&width=90pc)

#### Tái sử dụng cấu hình C++ của bạn

VS Code giờ đã được cấu hình để sử dụng trình biên dịch Microsoft C++. Cấu hình này áp dụng cho workspace hiện tại. Để tái sử dụng cấu hình, chỉ cần sao chép các tệp JSON vào thư mục `.vscode` trong một thư mục dự án mới (workspace) và thay đổi tên của (các) tệp nguồn và tệp thực thi khi cần.

#### Chạy VS Code bên ngoài Developer Command Prompt

Trong một số trường hợp nhất định, không thể chạy VS Code từ **Developer Command Prompt for Visual Studio** (ví dụ: trong các kịch bản Remote Development thông qua SSH). Trong trường hợp đó, bạn có thể tự động hóa việc khởi tạo **Developer Command Prompt for Visual Studio** trong quá trình build bằng cách sử dụng cấu hình `tasks.json` sau:

```json
{
    "version": "2.0.0",
    "windows": {
        "options": {
            "shell": {
                "executable": "cmd.exe",
                "args": [
                    "/C",
                    // Đường dẫn đến VsDevCmd.bat phụ thuộc vào phiên bản Visual Studio bạn đã cài đặt.
                    "\"C:/Program Files (x86)/Microsoft Visual Studio/2019/Community/Common7/Tools/VsDevCmd.bat\"",
                    "&&"
                ]
            }
        }
    },
    "tasks": [
        {
            "type": "shell",
            "label": "cl.exe build active file",
            "command": "cl.exe",
            "args": [
                "/Zi",
                "/EHsc", 
                "/Fe:",
                "${fileDirname}\\${fileBasenameNoExtension}.exe",
                "${file}"
            ],
            "problemMatcher": [
                "$msCompile"
            ],
            "group": {
                "kind": "build",
                "isDefault": true
            }
        }
    ]
}
```

>**Lưu ý**: Đường dẫn đến `VsDevCmd.bat` có thể khác tùy thuộc vào phiên bản Visual Studio hoặc đường dẫn cài đặt. Bạn có thể tìm đường dẫn đến `VsDevCmd.bat` bằng cách mở Command Prompt và chạy `dir "\VsDevCmd*" /s`.

#### Xử lý sự cố

#### Thuật ngữ 'cl.exe' không được nhận diện

Nếu bạn thấy lỗi "The term 'cl.exe' is not recognized as the name of a cmdlet, function, script file, or operable program", điều này thường có nghĩa là bạn đang chạy VS Code bên ngoài **Developer Command Prompt for Visual Studio** và VS Code không biết đường dẫn đến trình biên dịch `cl.exe`.

VS Code phải được khởi động từ Developer Command Prompt for Visual Studio, hoặc task phải được cấu hình để [chạy bên ngoài Developer Command Prompt](#run-vs-code-outside-the-developer-command-prompt).

Bạn luôn có thể kiểm tra xem mình có đang chạy VS Code trong ngữ cảnh của Developer Command Prompt hay không bằng cách mở Terminal mới (`kb(workbench.action.terminal.new)`) và gõ 'cl' để xác minh `cl.exe` có sẵn cho VS Code.

#### lỗi nghiêm trọng C1034: assert.h: không có đường dẫn include nào được thiết lập

Trong trường hợp này, `cl.exe` có sẵn cho VS Code thông qua biến môi trường `PATH`, nhưng VS Code vẫn cần được khởi động từ **Developer Command Prompt for Visual Studio**, hoặc được cấu hình để [chạy bên ngoài Developer Command Prompt](#run-vs-code-outside-the-developer-command-prompt). Nếu không, `cl.exe` không có quyền truy cập vào các biến môi trường quan trọng như `INCLUDE`.

#### Các bước tiếp theo

- Khám phá [Hướng dẫn Người dùng VS Code](/docs/editor/codebasics.md).
- Xem lại [Tổng quan về tiện ích mở rộng C++](/docs/languages/cpp.md).
- Tạo một workspace mới, sao chép các tệp JSON `.vscode` của bạn vào đó, điều chỉnh các cài đặt cần thiết cho đường dẫn workspace mới, tên chương trình, và v.v., và bắt đầu lập trình!
