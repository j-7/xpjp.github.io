---
layout: post
title:  "旧ウォレット 1.0.0 のままハードフォーク(2018/1/1 09:00)を迎えられた方向けの移行手順について"
date:   2018-1-6 15:30:00 +0900
categories: official
author: 依田
---  
XP-JP Labチームからのお知らせです。  
旧ウォレット 1.0.0 のままハードフォーク(2018/1/1 09:00)を迎えられた方は下記の手順に従いウォレットの移行を行ってください。  
また既にご自身で1.1.0に移行し、ブロックの同期が進まない方や残高の表示が正しく表示されない方も下記の手順を行い残高の表示が正しくなるか確認をしてください。  

<br>
<hr>

・bootstrap.dat を[ダウンロード](https://object-storage.tyo1.conoha.io/v1/nc_c17ae3d951a84d7ba2a9d28bf2bbfbd7/XPbootstrap/bootstrap.dat)  
・現在のXPフォルダをバックアップしてください。  
・`wallet.dat peers.dat XP.conf` **以外**のファイルを消す  
・`bootstrap.dat` を置く  
・XPウォレット 1.1.0 を導入し起動する（起動には数十分～数十時間掛かります）  
・`bootstrap.dat` が消え、 `bootstrap.dat.old` が出来ていれば作業は完了です。   ※bootstrap.dat.old は不要ですので削除してください。  

<hr>
<br>

以上となります。  
上記の作業で表示された残高が現在の残高となります。  

<br>
FAQ  

Q:旧ウォレットより送ったXPが相手に届いていない  
A:ハードフォーク以降に生成されたXPを含める形で送付していた場合は取引が存在しないものとして処理されます。  
[https://chainz.cryptoid.info/xp/](https://chainz.cryptoid.info/xp/) にてトランザクションを検索し、存在しない場合は改めてXPをお送りください。  


Q:旧ウォレットの時より残高が減っている (2018/1/1 09:00 以降にXPを受け取っていた場合)  
A:送り主が旧ウォレットでハードフォーク以降に生成されたXPを含める形で送付していた場合は取引が存在しないものとして処理されます。  
[https://chainz.cryptoid.info/xp/](https://chainz.cryptoid.info/xp/) にてトランザクションを検索し、存在しない場合は送り主に対し新ウォレットで再送するよう依頼してください。  


Q:旧ウォレットの時より残高が減っている (2018/1/1 09:00 以降に鋳造/マイニングが成功していた場合)  
A:旧ウォレットでハードフォーク以降に成功したと表示されている鋳造/マイニング報酬はすべて無効です。  
新ウォレットでは報酬は存在しないものとして処理されます。  