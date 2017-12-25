---
layout: post
title:  "Game Balance の残高不一致についての見解"
date:   2017-12-24 21:10:00 +0900
categories: official
author: 依田
---  
XP-JP Mods & Lab チームからのお知らせです。  
先ほどお伝えしました Xp-Bot の不具合について、本家Mod babyfist さんに見解をお聞きしました。  

・deposit にて Game Balance に入金された XP は、その処理において入金以上に増えることはない。  
・同じトラザクション処理が複数表示されたとしても、実際の処理は一度だけである。  
・Game Balance の 正しい残高以上の rain や withdraw はできない。

しかし、以下のことが確認されました。  

・deposit による入金先アドレスは全ユーザー共通のものであり、ユーザーごとの管理や rain については別途データベースによる管理であるということ (後半は推測)。  
・deposit で入金した際に、複数のTXが表示され、かつ入金額が数倍レベルで一致しない。  
・上記を確認したあとの withdraw において、正しくないはずの Game Balance と ほぼ同額の引き落としができたこと。  

というところから、以下のことが推測されます。  

・過負荷もしくはバグにより Xp-Bot と Game Balance を管理するデータベースとのやり取りの処理が乱れ、Game Balance の表示に大きな誤差が生まれること。  
・Game Balance の 正しい残高以上の rain や withdraw は、本来できないにも関わらず、トラザクション処理を経ないデータベース処理によって行われてしまっていること。  

結果として、トラザクションの情報と Game Balance のデータベースとの不一致が発生し、Game Balance 上の残高は最悪でGOX、もしくはロールバックの可能性が考えられます。  

つきましては、本家の発表があるまでは deposit withdraw および rain 機能を使わないことを推奨します。  

以上、推測ではありますが見解をあげさせていただきます。  