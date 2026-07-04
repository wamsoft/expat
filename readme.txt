Title: expat plugin
Author: わたなべごう

●これはなに？

 expat を使って XML を処理するパーサプラグインです。
 XMLParser クラスを登録します。パース中は対象オブジェクトの startElement /
 endElement / characterData / comment / processingInstruction / cdata 等の
 メソッドがコールバックされます (DOM 実装例は XML.tjs 参照)。

 ※本プラグインは旧 Win32 専用実装を全ビルドバリアント(WIN/SDL/LIB)対応へ
   近代化したものです。windows.h/DllMain/WideCharToMultiByte/IStream 等の
   Win32 依存を撤去し、UTF-8<->UTF-16 変換はエンジン提供の
   TVPUtf8ToWideCharString / TVPWideCharToUtf8String を、ファイル入力は
   iTJSBinaryStream(TVPCreateStream) を使用。クラス登録は ncbind 化しています。

●コンパイル方法

 vcpkg で expat が必要です (vcpkg.json 参照)。VCPKG_ROOT を設定した状態で
 umbrella の CMake ビルドに含めれば自動で解決されます。expat は静的リンク
 されるため配布時に別途 DLL は不要です。

●使い方

  manual.tjs と XML.tjs を参照

●ライセンス

Copyright (c) 1998, 1999, 2000 Thai Open Source Software Center Ltd
                               and Clark Cooper
Copyright (c) 2001, 2002, 2003, 2004, 2005, 2006 Expat maintainers.

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be included
in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

このプラグイン自体のライセンスは吉里吉里本体に準拠してください。
