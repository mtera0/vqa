# vqa
## 1.プロジェクト内容
概要：
量子コンピュータのうちVQAに関連する基本的なコード。

詳細：
量子コンピュータでは、情報を量子ビットという量子状態として扱う。回路がビットを様々な情報として表現することに対応して、量子ビットを種々の量子状態に変化させるものもしくは表現された量子状態そのものは量子回路と呼ばれる。量子ビットや量子回路を活用することで、量子コンピュータは従来のコンピュータとは異なる優れた計算処理の可能性が期待されている。

そして量子コンピュータの応用先のうち、シミュレーションに利用される技術として量子変分アルゴリズム（Variational Quantum Algorithm, VQA）がある。これはシミュレーションにおいて求めたい量子状態になるべく近い状態を量子回路で表現するものである。例えば、最もエネルギーの低い状態をシミュレートしたい場合には、機械学習でいうところのcost関数にエネルギーを設定すれば、勾配が小さくなる方向へ量子回路のパラメータを最適化していくことでVQAを利用したシミュレーションが実装できる。

しかしながら、VQAを利用していく上でいくつかの問題が立ち塞がっている。そのうちの一つがBarren plateauである。Deep Neural Networkの文脈においても知られている問題で、例えば量子回路の大きさ（より正確には量子ビット数や量子回路の深さなど）が大きくなると、パラメータの最適化時に利用する勾配が非常に小さくなることから、パラメータ更新が困難となってしまうというものである。量子コンピュータにおいては[Barren plateaus in quantum neural network training landscapes](https://arxiv.org/pdf/1803.11173)で最初に確認された。本リポジトリではこの論文の内容を参考に実装している。

本リポジトリではVQAのうち以下を作成している。
* 基底状態を求める量子変分固有値ソルバー（Variational Quantum Eigensolver, VQE）の基本的なコード
* Barren plateauを確認するコード

## 2.主要技術

| 言語・モジュール | バージョン |
| -------------------- | ---------- |
| Python                | 3.9.12       |
| matplotlib                | 3.6.2       |
| numpy                | 1.21.6       |
| qulacs                | 0.5.5       |
| qulacsvis                | 0.4.0       |
| quspin                | 0.3.6       |
| scipy                | 1.7.3       |

## 3.開発環境構築方法

#### 1. Python のインストール

Python をインストール。インストール方法は[公式ドキュメント](https://www.python.org/downloads/)を参照。

#### 2. 必要なモジュールのインストール

[matplotlib](https://matplotlib.org/stable/users/getting_started/), [numpy](https://numpy.org/ja/install/), [scipy](https://scipy.org/install/), [qualcs](https://docs.qulacs.org/ja/latest/intro/1_install.html), [qulacsvis](https://github.com/Qulacs-Osaka/qulacs-visualizer), [quspin](https://quspin.github.io/QuSpin/Installation.html) のうちインストールしていないものがあれば各リンク先のコマンドによりインストール
