# SISideBar
インストール

    Clone or download > Download ZIP からZIPファイルをダウンロードしてください。

    解凍したSiSideBarフォルダを C:\Program Files\Autodesk\ApplicationPlugins へコピーしてください。
    
    MayaをCドライブ以外にインストールしている場合でもSiShelfフォルダは
    C:\Program Files\Autodesk\ApplicationPlugins
    に置く必要があるようです。

    ApplicationPluginsフォルダが存在しない場合は作成してください。

    動作確認はMaya2014～2018で行っています。
    
    ---------------------------------------------------------
    ・2013 × 確認できてません
    ・2014 △ ドッキングできません、平面ハンドルとのリンクができません、Uni/Volモードが不安定
    ・2015　〇 平面ハンドルとのリンクができません
    ・2016　◎ 特に問題なし
    ・2017　〇 UI周りの描画がおかしくなることがある（2017のバグかも）
    ・2018　◎ 特に問題なし
    ---------------------------------------------------------
    
    設定ファイルは
    C:\Users\[User_Name]\Documents\maya\Scripting_Files
    に生成されます。
    不具合が発生した場合は削除してみると直るかもしれません。

    不要になった場合はフォルダを削除してください。
    
    インストールに成功するとウィンドウメニューにSiSideBarが追加されます。
    
    Readmeはこれからかくです。
    Maya起動時に前回の終了状態でウィンドウ位置、ドッキング位置を復元します。
    
![20171113-212852](https://user-images.githubusercontent.com/28256498/32726190-6982b406-c8bb-11e7-9c9d-25a018194a1a.jpg)
![2017-11-13_23h23_06](https://user-images.githubusercontent.com/28256498/32730253-d5b4e294-c8c9-11e7-9c9c-0d21e2a5c8e8.png)


主な機能
    
    ・SRT選択状態のリンク

    ・マニピュレータのXYZ軸との相互リンク

    ・SRT入力窓の再現
    ・四則演算入力のSI方式とMaya方式の両立（10+、+=10など）
    ・計算式入力対応 (1*(3+5))/25+3 とか
    ・ランダム関数入力 r→0～1, r(n)→0～n, r(n,n2)→n～n2, r(n,n2,s)シードをsで整数指定、同じシードなら同じ乱数が返ってくる
    ・ホイール入力への対応（Shift,Ctrlで桁調整 10, 1, 0.1）
    ・カッコ[ ]による数値追加入力に対応 通常1.0ずつ、 shift 0.1ずつ、ctrl 10ずつ
    ・スペース入力は0.0扱い
    ・コンポーネントへの入力対応
    ・3軸ボタン、を右クリックで一括入力
    
    
    ・マウスジェスチャー入力に対応
    入力窓をクリック＆ドラッグで数値加算できます。
    右側にドラッグすると加算、左で減算。
    SIは対角で+-、-+となってましたがわかりにくいので仕様変更。
    円を描くようにすると続けて加算できます。
    Uターンすると符号反転（+-切り替え）します。Uターン角度の閾値は現在120°
    Shiftで+-0.1、Ctrlで+-10
    
    ・オブジェクト名検索、スペース区切りで複数ワード検索可能　例）pShper* pCube*
    ・検索タイプのフィルター機能、右クリックでオプションメニューオープン
    ・コンポーネント検索 コロン区切りで連続指定、スペース区切りで複数指定 例）1:50 60:75 90
    

    ・FreezeMの再現（ヒストリをベイクしてウェイトを書き戻し、クラスタとブレンドシェイプは保護）
    ・ラティスをウェイトつけたままベイクできます
    ・ウェイトをミュートしてからFreezeMするとバインドポーズを簡単に変更できます
    ・とりあえずかけておくとメッシュにまつわる大概の不具合が解消します

    ・Freezeの再現

    ・トランスフォームスペースのリンク（Global, Local, View, Objectなど）

    ・VolモードUniモードの再現

    ・Transformメニュー再現、拡充
    ・ResetActor
    ・JointOriento↔Rotation
    ・MutchiTransform
    ・FreezeTransform
    ・ResetTransform
    ・MoveCenterToSelection
    ・絶対値に移動

    ・アニメーションキーボタンをついか（右クリックで3軸一括設定）

    ・センターモードでセンターを移動

    ・Groupモードで選択したオブジェクトが属するセットを逆引き選択

    ・Clusterモードで選択したコンポーネントが属するクラスタ、セットを逆引き選択

    ・UIメニューの折り畳み
    
    ・UIカラーの切り替え

    ・MayaシーンファイルをUIへのドラッグドロップでOpenScene扱いで開けます。自動でSetProjectされます。

    ・Numpyモジュールがインストールされているとコンポーネント計算が3倍くらい早くなります

    ・とりあえず使用説明動画とってみました
https://youtu.be/14T5_Ak4dAE
https://youtu.be/Ymq6SQwWF8s
https://youtu.be/tC5p24b9sUQ

更新履歴

    2017/11/20 ver2.0.9
     ・Linear関数の実装 randam関数、マルチライン入力との併用も可能（需要あるのか？？）
     ・オブジェクトモードのセンターオブジオメトリ機能追加 
     ・Nurbs,Curveタイプへの対応が不完全だった部分を修正 
     ・2.0.8での2次バグ修正
    
    2017/11/19 ver2.0.8
     ・2018のコンポーネントモード仕様変更に対応
     ・2018特定の条件で落ちる不具合を修正
     ・トランスフォーム軸スペース名をMaya準拠に変更
     ・Uni/Volモードのボタンを1つに統一、代わりにCompoentボタンを挿入
     
    2017/11/18 ver2.0.7
     ・マウスジェスチャー入力に対応
     ・アトリビュートの表示桁数変更に対応
     ・アトリビュートの小数点丸め機能実装
     ・マルチライン入力の改善と不具合対応
    
    2017/11/17 ver2.0.6
     ・絶対値に移動の計算誤差修正 
     ・絶対値に移動を設定しているときのコンポーネント回転、スケールの不具合を修正
     ・基本的な計算式入力に対応（例）1+2*(10-3)/5など
     ・ランダム関数に対応 
     書式：r→0～1, r(n)→0～n, r(n,n2)→n～n2, r(n,n2,s)シードをsで整数指定、同じシードなら同じ乱数が返ってくる
     ・'[',']'　カッコによる数値入力に対応、shift, ctrlでそれぞれ0.1ずつ、10ずつの入力に
    
    2017/11/16 ver2.0.5
     ・絶対値に移動追加 
     ・トランスフォームメニューをローカライズ 
     ・Maya2014への対応（※ドッキングできません）
    
    2017/11/15 ver2.0.4
     ・2017,2018での起動時ドック状態の復元に対応 
     ・Match_Transformのバグ修正（開発環境では起きにくい特殊なバグでした…） 
     
    2017/11/15 ver2.0.3
     ・Trans入力で掛算割り算が効かなかったのを修正 
     ・Curve、Nurbsタイプのコンポーネント選択に対応
    
    2017/11/14 ver2.0.2
     ・英語版のメッセージ不具合対応 
     ・2016Extention2の起動時エラー対応  
     ・スケールUni/Volモード不具合対応 
     ・COGモードのローテーションがスペース設定によっては効かなかったのを修正
     
    2017/11/13 ver2.0.1
     ・入力窓にスペースを打つと0.0になるように変更
     
    2017/11/12 ver2.0.0 リリース
    
