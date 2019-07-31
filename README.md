# Ansible Role: ntp
chronydまたはntpdを用い、ntpクライアントまたはntpサーバーの設定をします。

## Sub Role: chrony
chronyサービスを用いてNTPクライアントまたはサーバーの設定を行います。
### 要件
無し
### 基本情報
- 依存ロール: 無し
- 冪等性: 有り
- 対応OS: RHEL7
- テスト環境: RHEL7.3
### 変数
- `NTP_SERVERS`
```yaml
# 参照先のNTPサーバーを設定します。
NTP_SERVERS:
  - ntp1.jst.mfeed.ad.jp
  - ntp2.jst.mfeed.ad.jp
  - ntp3.jst.mfeed.ad.jp
```
- `NTP_CHRONY_LEAPSEC`
```yaml
# うるう秒発生時の動作を設定します。
NTP_CHRONY_LEAPSEC: slew
```
- `NTP_CHRONY_ALLOWS`
```yaml
# 接続を許可するネットワークを設定します。この設定を行うと、chronyはNTPサーバーとして動作します。
NTP_CHRONY_ALLOWS:
  - 192.168.19.0/24
  - 192.168.29.0/24
  - 192.168.39.0/24

# 以下の通り空のリストを設定すると、NTPクライアントとして動作します。
NTP_CHRONY_ALLOWS: []
```

## Sub Role: ntpd
未作成。