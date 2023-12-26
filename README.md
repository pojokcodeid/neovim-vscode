# PANDUAN INTEGRASI NEOVIM - VSCODE

## Pastikan Sudah Install VSCode

## Pastikan Sudah Install NeoVim

## Install Extension Di VSCode

- https://marketplace.visualstudio.com/items?itemName=asvetliakov.vscode-neovim
- https://marketplace.visualstudio.com/items?itemName=VSpaceCode.whichkey

## Configurasi Neovim

- Masuk ke configurasi Neovim (sesuaikan dengan system oprasi masing-masing)
- Cek konfigurasi di `~/.config/nvim/init.lua` untuk linux dan maxOS
- Cek konfigurasi di `$HOME/AppData/Local/nvim/init.lua` untuk windows
- Tambahkan code berikut

```lua
if vim.g.vscode then
  -- config vscode
	Map = vim.keymap.set
	Cmd = vim.cmd
	VSCodeNotify = vim.fn.VSCodeNotify
	VSCodeCall = vim.fn.VSCodeCall

	require("vscode.functions")
	require("vscode.mappings")
else
  -- config neovim
	require("core")
end
```

- Buat file `function.lua` di `~/.config/nvim/lua/vscode` untuk linux dan maxOS
- Buat file `mappings.lua` di `~/.config/nvim/lua/vscode` untuk linux dan maxOS
- Buat file `function.lua` di `$HOME/AppData/Local/nvim/lua/vscode` untuk windows
- Buat file `mappings.lua` di `$HOME/AppData/Local/nvim/lua/vscode` untuk windows
- Contoh isi code `function.lua, mappings.lua` : ada di folder code/vscode

## Lakuan config di VSCode

- Buka setting.json
- Contoh Config di folder code
