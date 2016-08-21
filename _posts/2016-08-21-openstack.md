---
layout: post
title:  "openstack workshop筆記"
desc: "openstack目的在於實現一個雲操作系統，一個具有部署與管理公有雲、私有雲以及混合雲架構iaas能力的平台。"
keywords: "openstack,blog,cloud"
date: 2015-01-08
categories: [cloud]
tags: [openstack,cloud]
icon: fa-bookmark-o
---


# openstack workshop
2014\/08\/21  Jack Lai 台灣威網 產品經理與技術顧問
---

物聯網的特性-&gt;透過url去access-&gt;物件儲存器

openstack至今已經六年了。

openstack目的在於實現一個雲操作系統，一個具有部署與管理公有雲、私有雲以及混合雲架構iaas能力的平台。

## vm vs instance

任何可以被處理運算的單元都是instance，他可能是硬體、vm、container、應用程式。openstack偏向一般作業系統在做的事情。

## openstack是什麼？

是一個框架、一個可以建立公有雲和私有雲的基礎架構。這必不是一個現成的產品，要想開展基礎架構方面的工作，企業需要顧問和開發人員。很多時候還需要第三方的集成工具。

因為不是產品所以初期導入時，需要有人幫忙安裝部署。\(like sap\)

## 三大核心區塊

大部分的iaas都會透過這三個方向來做設計

1. computing \(cpu 在處理process\)

2. networking\(data center雲操作系統，有許多運算單元，nova在處理這個東西\)

  data center 上面有些網路設備，上面可能要設定一些config，有時候可能會打錯，全部就要重打，透過openstack的指令方式執行，他會直接幫我們設定他\(只要那個設備有neutron api\)，統一介面可以直接 config好。
3. storege\(儲存東西\)

  openstack的storege大約分成三大塊 swift sinder 馬尼拉（在openstack中可以透過 restful url的方式來存取他的儲存空間），參考（http:\/\/www.csdn.net\/article\/2013-03-29\/2814703）
  fat32 上限是4G，最大是2TB，傳統的檔案系統會遇到單一檔案的大小的問題，object的話會把它切成小塊小塊來進行儲存。

## DeCore

現在openstack越來越成熟，是因為Decore越來越穩定的原因。有幾個元件是部署openstack一定要有的元件。

## BigTent

有額外需要的東西就，就另外再加。

所有看到的部署工具都會把這些東西安裝進去

1. Glance 

2. neutron

3. swift

4. keystone

5. cinder

6. nova


其他如果有需要的話就可以自己額外的加進去。
## openstack的問題是什麼？

1. 難用

2. 難掌握

3. 不易維護造成難以維運

4. 初期導入成本高 人力、物力、財力

5. 版本次頻率太快-企業組織無發跟上腳步

6. 相容性問題-自己的程式碼 社群的程式碼


## 企業會想要怎麼樣的平台

1. 高可用

2. 穩定

3. 安全效能高

4. 易維護

5. 易使用

6. 便宜


## 企業不會想要的是怎樣的雲平台

1. 降低工作效率

2. 難操作

3. 找不到人才可以管理雲平台

4. 耗時耗資源

5. 影響企業核心價值

6. 不一定想知道底層的技術


## 企業級OpenStack部署套件

1. 高可用

2. 高擴充

3. 高度彈性

4. 友善的安裝環境


## OpenStack痛處

1. 設定檔太複雜

2. 太難駕馭

3. 升級為運不見

4. 服務不中斷

5. 網路環境


## JUJU MAAS

適用於ubuntu的部署工具。

＃用14版的ubuntu\(http:\/\/www.ubuntu.com\/download\/cloud\/install-openstack-with-autopilot\)

## FUEL

fuel很多東西都是給全UI的，開個瀏覽器就可以進去。利用企業部署的軟體，會比較知道IT想要什麼。

＃切記如果運用fuel的話需要兩張網卡。\(https:\/\/github.com\/openstack\/fuel-virtualbox\)

## Crowbar

suse用的部署套件。

## RDO

單機上面很容易做openstack的部署。\(https:\/\/www.rdoproject.org\/\)

## KOLLA

1. 用docker來部署openstack服務

2. 簡化部署以及升級維運時的操作與管理

3. 可以有機會做到開箱即用的管理好處

4. kolla的意思是膠水要把OpenStack和docker很好的黏在一起

5. 目前最熱門的專案之一


