# Golang-learning
## My First Go Project

這是一個用 Go 語言撰寫的練習專案，目的是熟悉 Golang 的語法與基本開發流程

## 🙏 參考來源
本專案參考自 [twtrubiks](https://github.com/twtrubiks) 的相關內容，特此致謝 🙇‍♂️

## 📦 專案功能

- Hello World 程式
- 基本的 CLI 輸入處理
- 簡單的函式與結構體應用

## 🛠️ 安裝與執行


### Clone 專案

git clone 

### 📁 專案結構

Golang-learning/
├── main.go       # 主程式
├── go.mod        # Go 模組描述檔案
└── README.md     # 本說明文件

### Golang 安裝

先到官網 [https://go.dev/doc/install](https://go.dev/doc/install) 下載



設定環境變數 Go 語言本身的執行檔路徑 (永久設定到 .bashrc)
```bash
vim ~/.bashrc
```

```vim
export PATH=$PATH:/c/Program\ Files/Go/bin
```

```bash (讓設定生效)
source ~/.bashrc
```

查看版本

```bash
go version
```

#### vscode 開發環境

安裝擴充套件 Go Team at Google go.dev (選最多人安裝的那個就對了)

如果它叫你自動安裝你就選 點擊 Install All 安裝它所依賴的工具 (特別是 gopls 和 dlv)。

#### gopls

gopls 是 Go 團隊官方開發的「語言伺服器」(Language Server)。

安裝指令

```cmd
go install golang.org/x/tools/gopls@latest
```

查看版本

```cmd
gopls version
```

設定環境變數

```cmd
vim ~/.zshrc
```

```txt
export PATH=$PATH:$(go env GOPATH)/bin
```

#### dlv

dlv (Delve 的縮寫) 就是 Go 語言的官方偵錯工具 (debugger)

```bash
go install github.com/go-delve/delve/cmd/dlv@latest
```

設定環境變數, Go 工具的安裝路徑

```bash
vim ~/.bashr
```

```vim
export PATH="$PATH:/c/Users/SCE/go/bin"
```

確認是否安裝成功

```bash
dlv version
```

#### 初始化以及 hello-world

接著開始前記得初始化專案, 「初始化」為一個 Go 模組 (Go module)

目前的 Go 語言開發都依賴一個名為 go.mod 的檔案來管理專案和其使用的第三方套件 (dependencies)

```bash
go mod init hello-world
```
創建hello.go
```go
//  1. 宣告這個檔案屬於 main 套件 (package)
//     只有 main 套件才能被編譯成可執行檔
package main

// 2. 導入 (import) "fmt" 函式庫
//    "fmt" 包含了格式化 I/O (輸入/輸出) 的函式，例如列印到終端機
import "fmt"

// 3. 程式執行的入口：main 函式 (function)
func main() {
	// 使用 fmt 套件中的 Println 函式，它會將文字印出並換行
	fmt.Println("Hello, World!")
```

執行

```bash
❯ go run hello.go
Hello, World!
```

💡 額外提示：
未來當你在專案中加入新的第三方套件 (import "some/package") 後，可以執行 go mod tidy 指令，它會自動幫你更新 go.mod 檔案，新增所需的套件並移除未使用的套件，是個管理專案的好習慣。
