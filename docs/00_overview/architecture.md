**目的:** 患者ブラウザから院内復元までの “１本道” を 1 枚絵で把握する。

```mermaid
flowchart TD
    subgraph Client[外部ネットワーク]
        user[患者ブラウザ] -- 入力フォーム --> forms[フォーム静的アプリ]
        forms -- 生成QR --> camera[スマホカメラ]
    end

    subgraph HospitalLAN[院内ネットワーク]
        camera -- 読取 --> reader[読み込みアプリ]
        reader -- 解析JSON --> backend[復元スクリプト]
    end
eof
