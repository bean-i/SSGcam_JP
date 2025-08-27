## 📱 ボイスフィッシング検知アプリ | SSGcam
<img src="https://github.com/bean-i/SSGcam/assets/86592841/35e7be72-f66e-49c5-bf02-843744549c5f" style="width: 100%;">

## 💡 プロジェクト概要  
- **アプリ名**: SSGcam
- **開発期間**: 2024年3月 ~ 2024年6月
- **開発体制**: 4人チーム
- **開発目的**:  
  - 通話内容をリアルタイムに解析し、**ボイスフィッシング**や**ディープボイス**を検知  
  - AIによる分析結果をモバイルアプリ上で**直感的にユーザーへ提示**  

## ✅ 主な機能  
- **1. 会員登録・ログイン**
  - 必要な権限（マイク・通知など）を許可  
- **2. ボイスフィッシング検知**
  - 通話中の最初の **4文** をSTTで変換し、AIサーバで判定 → 疑わしい場合は通知（バナー／音／振動）  
- **3. ディープボイス検知**
  - 通話開始から **10秒間の音声** をAIサーバで分析し、疑わしい場合は通知を表示  
- **4. 検知記録**
  - 検知された通話をアプリ内に保存し、後で再生可能
- **5. チャットボット**
  - ボイスフィッシング対処法や口座振込停止手続きなど、主要なFAQを案内

## 💻 技術スタック  
- **フロントエンド**: `Flutter`, `Swift`  
- **バックエンド**: `Node.js`, `MongoDB`  
- **AI/ML**: `TensorFlow`, `Keras` 

## ⚙️ アーキテクチャ概要  
- **クライアント（Flutter）** ↔ **サーバ（Node.js）** ↔ **AIモデルサーバ／DB（MongoDB）**  
- サーバは **STT結果を収集し、AIモデルと連携して判定結果をアプリへ返却**
<img src="https://github.com/bean-i/SSGcam/assets/86592841/a891a079-4348-4b62-ae51-c5cdb3013bd9" style="width: 80%;">


## 👨‍💻 担当範囲  
- **Flutterを用いたアプリ開発**: UI/UX設計・実装、サーバAPI連携  
- **バックエンド開発**: `STT結果の収集 → AIサーバ判定 → アプリ通知までの送信ロジックを実装` 

## 🔎 工夫した点  
- **リアルタイム処理の最適化**  
  - Google STTの結果を文単位で収集し、**4文ごとにサーバへ送信**する設計  
  - 遅延（レイテンシー）を抑え、ユーザーへ迅速に警告を表示  
- **iOS通知機能の実装**  
  - Flutterのみでは制約のあったiOS通知処理を **Swift（AppDelegate）＋ flutter_local_notifications** で補完  
  - **バナー／振動／サウンド通知** を安定的に提供し、ユーザー体験を改善  

## 📷 画面
| ボイスフィッシング検知 | 検知記録 | 疑わしい番号検索 | チャットボット |
|:--:|:--:|:--:|:--:|
| <img width="1179" height="2556" alt="IMG_1512 2" src="https://github.com/user-attachments/assets/23d384bb-bf8b-4f92-873a-2f0e569d11d1" /> | <img width="1179" height="2556" alt="IMG_1513" src="https://github.com/user-attachments/assets/ca10563d-b9a3-48ae-8650-1336ed82b983" /> | <img width="1179" height="2556" alt="IMG_1516 2" src="https://github.com/user-attachments/assets/f345be13-6c8c-451a-9628-407b106f59dd" /> | <img width="1179" height="2556" alt="IMG_1515 2" src="https://github.com/user-attachments/assets/93ef885e-d0ee-4caa-8a13-e2d03f6d47c8" /> |
