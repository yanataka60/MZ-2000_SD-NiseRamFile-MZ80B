# MZ-2000_SD+偽RAMFILE複合ボード for MZ-80B

MZ-2000_SD+偽RAMFILE複合ボードのVGA出力はMZ-2000用でありMZ-80Bではまともな表示が出来ません。

https://github.com/yanataka60/MZ-2000_SD-NiseRamFile-

そこでMZ-80BでもVGA出力が正常に表示されるようにプログラムを修正しました。

変更はPico2のプログラムだけで基板はMZ-2000_SD+偽RAMFILE複合ボードをそのまま使います。

MZ-2000_SD+偽RAMFILE複合ボードからテキスト、グラフィックともカラー表示、カラーパレット機能、テキストとグラフィックのプライオリティ、カラー対応PCG機能を削除しています。

モノクロのPCG(FONT再定義)機能は残っていますが、MZ-2000_SD、EMM、VGA出力だけですからあまり魅力は無いと思いますが、GRAM1、GRAM2が装備されていなくともVGA出力からは正常に表示できるようにしたバージョンも作りましたのでGRAM1、GRAM2を装備していないMZ-80Bでは使う価値があると思います。

以下の機能があります。

・MZ-2000_SDの起動及びMZ-2000_SDの機能

・EMM1からの起動(ただし、EMM1にHu-BASICの起動ディスクイメージがある場合のみ)

・MZ-80Bのテキスト出力及びグラフィック出力をエミュレートしてVGA出力

・EMM1エミュレータ(320KByte)

・漢字ROMボードエミュレータ

・キャラクタ単位でFONTの変更(VGA出力のみ)

## 回路図
MZ-2000_SD+偽RAMFILE複合ボードを参照してください。

https://github.com/yanataka60/MZ-2000_SD-NiseRamFile-?tab=readme-ov-file#%E5%9B%9E%E8%B7%AF%E5%9B%B3

## 偽RAMFILE for MZ-2000の書込み
　GRAMの有無により3種類があります。環境に合わせてどちらかを選択してください。なお、「GRAM1のみ装着あり」「GRAM1、GRAM2とも装着無し」を選択してもMZ-80B本体モニタにGRAMが拡張されるわけではありません。VGA出力にのみグラフィックが正常に出力されます。

### GRAM1、GRAM2とも装着あり
　RP2350Bフォルダにあるniseramfile.uf2をRP2350Bマイコンボードに書き込みます。

　MZ-2000、MZ-2500の2000モードで使用した場合、MZ-2000_SD機能、EMM1エミュレータ、漢字ROMボードエミュレータは問題なく動作しますが、VGA出力機能はVRAM、GRAMのアクセス方法がMZ-80Bと異なるためまともな表示となりません。

### GRAM1のみ装着あり(GRAM2エミュレート)
　RP2350Bフォルダにあるniseramfile_GRAM1_Only.uf2をRP2350Bマイコンボードに書き込みます。

　グラフィックボートGRAM2が装着されていないこと。

　MZ-2000、MZ-2500(80B、2000、2500モードとも)では正常に動作しません。通常のバージョンniseramfile.uf2を使ってください。

### GRAM1、GRAM2とも装着無し(GRAM1、GRAM2エミュレート)
　RP2350Bフォルダにあるniseramfile_No_GRAM.uf2をRP2350Bマイコンボードに書き込みます。

　グラフィックボートGRAM1、GRAM2とも装着されていないこと。

　MZ-2000、MZ-2500(80B、2000、2500モードとも)では正常に動作しません。通常のバージョンniseramfile.uf2を使ってください。

### 書込み
　RP2350BのBOOTボタンを押しながらUSB-Cケーブルを接続するとパソコンがUSBメディアとして認識しますのでniseramfile.uf2をドロップすると自動的に書き込まれます。

　書き込みが終了するとパソコンからはUSBとして見えなくなりますのでそうなったらケーブルを抜いて終了です。

## MZ-2000_SD BOOT PROGRAMをMZ-1R12 SRAMメモリ 0番バックアップスロットへ書き込み
MZ-2000_SD+偽RAMFILE複合ボードを参照してください。

https://github.com/yanataka60/MZ-2000_SD-NiseRamFile-?tab=readme-ov-file#mz-2000_sd-boot-program%E3%82%92mz-1r12-sram%E3%83%A1%E3%83%A2%E3%83%AA-0%E7%95%AA%E3%83%90%E3%83%83%E3%82%AF%E3%82%A2%E3%83%83%E3%83%97%E3%82%B9%E3%83%AD%E3%83%83%E3%83%88%E3%81%B8%E6%9B%B8%E3%81%8D%E8%BE%BC%E3%81%BF

## FONTファイルの書込み
MZ-2000_SD+偽RAMFILE複合ボードを参照してください。

https://github.com/yanataka60/MZ-2000_SD-NiseRamFile-?tab=readme-ov-file#font%E3%83%95%E3%82%A1%E3%82%A4%E3%83%AB%E3%81%AE%E6%9B%B8%E8%BE%BC%E3%81%BF

## Arduinoプログラム
MZ-2000_SD+偽RAMFILE複合ボードを参照してください。

https://github.com/yanataka60/MZ-2000_SD-NiseRamFile-?tab=readme-ov-file#arduino%E3%83%97%E3%83%AD%E3%82%B0%E3%83%A9%E3%83%A0

## 拡張機能の使い方
MZ-2000_SD+偽RAMFILE複合ボードを参照してください。

### MZ-2000_SDの起動
MZ-2000_SD+偽RAMFILE複合ボードを参照してください。

https://github.com/yanataka60/MZ-2000_SD-NiseRamFile-?tab=readme-ov-file#mz-2000_sd%E3%81%AE%E8%B5%B7%E5%8B%95

### EMM1エミュレータ
MZ-2000_SD+偽RAMFILE複合ボードを参照してください。

https://github.com/yanataka60/MZ-2000_SD-NiseRamFile-?tab=readme-ov-file#emm1%E3%82%A8%E3%83%9F%E3%83%A5%E3%83%AC%E3%83%BC%E3%82%BF

### 漢字・辞書ROM MZ-1R13
MZ-2000_SD+偽RAMFILE複合ボードを参照してください。

https://github.com/yanataka60/MZ-2000_SD-NiseRamFile-?tab=readme-ov-file#%E6%BC%A2%E5%AD%97%E8%BE%9E%E6%9B%B8rom-mz-1r13

### FONT変更機能
MZ-2000_SD+偽RAMFILE複合ボードを参照してください。FONTカラー設定は出来ません。

https://github.com/yanataka60/MZ-2000_SD-NiseRamFile-?tab=readme-ov-file#font%E5%A4%89%E6%9B%B4%E6%A9%9F%E8%83%BD

## 開発環境、使用ライブラリなど
　開発環境は、Visual Studio Codeです。

　VGAライブラリは以下を使用しています。

- [VGA ライブラリ(一部改変)](https://github.com/vha3/Hunter-Adams-RP2040-Demos/tree/master/VGA_Graphics)

## 謝辞
　素晴らしい拡張モジュールを開発し、自由に改変・公開を快く承諾してくださったしっぽいいんちょさん、ありがとうございました。
