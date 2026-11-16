# 電子學筆記：PN 接面的電流方程式

## 0. 先備知識（上一講：未加偏壓的 PN 接面）

- 接面自己就有內建電場與內建電位 $V_0$（矽約 $0.6\sim0.8\ \text{V}$），來自多數載子擴散、複合後留下的固定離子（空間電荷）。
- 內建電位：

  $$V_0=V_T\ln\!\left(\frac{N_A N_D}{n_i^2}\right),\qquad V_T=\frac{kT}{Q}\approx25.9\ \text{mV}\ (300\ \text{K})$$

- 空乏區寬度：

  $$W=x_p+x_n=\sqrt{\frac{2\varepsilon_s}{Q}\left(\frac{1}{N_A}+\frac{1}{N_D}\right)V_0}\ \propto\ \sqrt{V_0}$$

- 電中性：$x_pN_A=x_nN_D$；接面電荷 $Q_J=QAN_Ax_p=QAN_Dx_n$。
- 計算順序：$N_A,N_D\to V_0\to W\to x_p,x_n\to Q_J$。
- 符號規則：下標 0 代表未加偏壓（例如 $W_0$、$x_{p0}$、$x_{n0}$），沒有下標 0 代表加偏壓後。

## 1. 反向偏壓（Reverse Bias）下的空乏區

**定義**：P 端接較低電位、N 端接較高電位，偏壓大小為 $V_R$（取正值）。

1. 外加電場 $\mathcal{E}_{apply}$ 方向為高電位指向低電位，即 N → P。
2. 內建電場 $\mathcal{E}_{BI}$ 方向也是 N → P，兩者**同向**。
3. 電場可疊加，總電場**增強**：$\mathcal{E}_{total}=\mathcal{E}_{BI}+\mathcal{E}_{apply}$。
4. 由高斯定理，電場增強代表空間電荷增加；固定離子密度由摻雜決定，只能靠空乏區**變寬**來多露出離子。
5. $x_{p0}\to x_p$、$x_{n0}\to x_n$、$W_0\to W$（皆變寬）。
6. 電場對寬度積分得到總電位差：

   $$V_0\ \longrightarrow\ V_0+V_R$$

7. 寬度與電荷量正比於總電位差的根號，把 $V_0$ 換成 $V_0+V_R$：

   $$W=\sqrt{\frac{2\varepsilon_s}{Q}\left(\frac{1}{N_A}+\frac{1}{N_D}\right)(V_0+V_R)}=W_0\sqrt{1+\frac{V_R}{V_0}}$$

   $x_p$、$x_n$、$Q_J$ 同理乘上 $\sqrt{1+V_R/V_0}$。

**數字例子**：$V_0=0.69\ \text{V}$，$W_0=0.42\ \mu\text{m}$，$V_R=5\ \text{V}$：

$$W=0.42\times\sqrt{1+\frac{5}{0.69}}\approx1.2\ \mu\text{m}$$

空乏區約變為原來的 3 倍。

## 2. 順向偏壓（Forward Bias）下的空乏區

**定義**：P 端接較高電位、N 端接較低電位，偏壓大小為 $V_F$（取正值）。

1. 外加電場方向為 P → N，與內建電場**反向**。
2. 總電場**變弱**：$\mathcal{E}_{total}=\mathcal{E}_{BI}-\mathcal{E}_{apply}$。
3. 需要的空間電荷變少，空乏區**變窄**：$x_{p0}\to x_p$、$x_{n0}\to x_n$、$W_0\to W$（皆縮小）。
4. 總電位差：

   $$V_0\ \longrightarrow\ V_0-V_F$$

   順向電壓抵消一部分內建電位，等於**降低位障**。

5. 把 $V_0$ 換成 $V_0-V_F$（需 $V_F<V_0$）：

   $$W=W_0\sqrt{1-\frac{V_F}{V_0}}$$

**數字例子**：$V_F=0.4\ \text{V}$：$W=0.42\times\sqrt{1-0.4/0.69}\approx0.27\ \mu\text{m}$。

**兩種偏壓對照**

| | 外加電場 vs. 內建電場 | 總電位差 | 空乏區寬度 |
|---|---|---|---|
| 反向偏壓 $V_R$ | 同向（相加）| $V_0+V_R$ | 變寬 |
| 順向偏壓 $V_F$ | 反向（相減）| $V_0-V_F$ | 變窄 |

## 3. 未加偏壓時中性區的載子濃度（基準值）

- P 側中性區：$p_{p0}\approx N_A$，$n_{p0}=\dfrac{n_i^2}{p_{p0}}\approx\dfrac{n_i^2}{N_A}$
- N 側中性區：$n_{n0}\approx N_D$，$p_{n0}=\dfrac{n_i^2}{n_{n0}}\approx\dfrac{n_i^2}{N_D}$
- 熱平衡無偏壓時，中性區內的載子濃度在空間中**均勻**，沒有濃度梯度，沒有擴散電流。

**數字例子**（$N_A=N_D=10^{16}\ \text{cm}^{-3}$，$n_i=1.5\times10^{10}\ \text{cm}^{-3}$）：多數載子約 $10^{16}$，少數載子 $n_{p0}\approx p_{n0}\approx2.25\times10^{4}\ \text{cm}^{-3}$。

## 4. 順向偏壓下的載子注入與擴散

**(1) 注入**

- 外加電場（P → N）對多數載子的作用力：P 側電洞往右、N 側電子往左，**都被推向空乏區**。
- 多數載子衝進空乏區，中和部分空間電荷，所以空乏區變窄。
- 位障降低後，P 側電洞可注入 N 側中性區，成為 N 側的少數載子（N 側電子也對稱地注入 P 側）。

**(2) 交界處濃度呈指數上升**（以 N 側為例，交界處 $x=x_n$）：

$$p_n(x_n)=p_{n0}\,e^{QV_F/kT}=p_{n0}\,e^{V_F/V_T}$$

**數字感受**：$V_F=0.6\ \text{V}$ 時 $e^{V_F/V_T}\approx1.2\times10^{10}$，少數載子由約 $2.25\times10^4$ 暴增至約 $2.6\times10^{14}\ \text{cm}^{-3}$。

**(3) 擴散並複合**

- 交界處濃度高、內部濃度低，注入的電洞向 N 側內部擴散。
- 擴散過程中遇到大量電子而被複合，多出來的濃度隨距離指數下降：

  $$p_n(x)=p_{n0}+p_{n0}\left(e^{V_F/V_T}-1\right)e^{-(x-x_n)/L_p}$$

**(4) 擴散長度與生存時間**

$$L_p=\sqrt{D_p\,\tau_p}$$

- $L_p$：擴散長度，少數載子被複合前平均能擴散的距離
- $D_p$：擴散常數（矽約 $12\ \text{cm}^2/\text{s}$）
- $\tau_p$：生存時間（lifetime），電洞被複合前平均存活的時間
- 活得越久、擴散能力越強，$L_p$ 越長
- 電子在 P 側同理：$L_n=\sqrt{D_n\tau_n}$

## 5. 推導電流方程式

**(1) 電洞擴散電流密度**（在 $x=x_n$）

由 $J_{p,\,diff}=-QD_p\dfrac{dp}{dx}$ 與上面的濃度分佈：

$$\frac{dp_n}{dx}=-\frac{p_{n0}}{L_p}\left(e^{V_F/V_T}-1\right)e^{-(x-x_n)/L_p}$$

$$J_{p,\,diff}(x_n)=\frac{Q\,D_p}{L_p}\,p_{n0}\left(e^{V_F/V_T}-1\right)$$

**(2) 電子擴散電流密度**（在 $x=-x_p$）

$$J_{n,\,diff}(-x_p)=\frac{Q\,D_n}{L_n}\,n_{p0}\left(e^{V_F/V_T}-1\right)$$

**(3) 總電流**（電流 = 面積 × 電流密度，兩種載子電流相加；各處總電流連續，所以在兩側交界處相加即可代表整個二極體的電流）

$$I=A\left(J_{p,\,diff}+J_{n,\,diff}\right)=A\left(\frac{QD_p\,p_{n0}}{L_p}+\frac{QD_n\,n_{p0}}{L_n}\right)\left(e^{V_F/V_T}-1\right)$$

括號外的係數只含材料參數（$D_p,D_n,L_p,L_n,p_{n0},n_{p0}$）與面積，**不含電壓**；電壓只出現在 $\left(e^{V_F/V_T}-1\right)$。

**(4) 代入 $p_{n0}\approx n_i^2/N_D$、$n_{p0}\approx n_i^2/N_A$，提出共同項 $Qn_i^2$**

$$I=A\,Q\,n_i^2\left(\frac{D_p}{L_pN_D}+\frac{D_n}{L_nN_A}\right)\left(e^{V_F/V_T}-1\right)$$

**(5) 定義飽和電流 $I_S$**

$$I_S=A\,Q\,n_i^2\left(\frac{D_p}{L_pN_D}+\frac{D_n}{L_nN_A}\right)$$

- $I_S\propto A$（接面面積）且 $I_S\propto n_i^2$。
- $n_i^2=BT^3\exp\!\left(\dfrac{-E_G}{kT}\right)$ 是溫度的強烈函式，所以 $I_S$ 與二極體電流也是溫度的強烈函式。
- $I_S$ 一般約 $10^{-18}\sim10^{-12}\ \text{A}$，非常小。

**(6) 最終結果（順向）**

$$\boxed{I_{PN}=I_S\left(e^{V_F/V_T}-1\right)}$$

**數字感受**（假設 $I_S=10^{-14}\ \text{A}$，$V_T=25.9\ \text{mV}$）：

| $V_F$ | $e^{V_F/V_T}$ | $I$ |
|---|---|---|
| 0.5 V | $2.4\times10^{8}$ | 約 2.4 μA |
| 0.6 V | $1.2\times10^{10}$ | 約 0.12 mA |
| 0.7 V | $5.5\times10^{11}$ | 約 5.5 mA |

電壓每增加約 $V_T\ln10\approx59.6\ \text{mV}$，電流變 10 倍；因此導通電壓看起來「約固定在 0.6～0.7 V」。

## 6. 反向偏壓下的電流

- 順向時交界處少數載子 $p_n(x_n)=p_{n0}e^{V_F/V_T}$；反向偏壓極性相反，把 $V_F$ 換成 $-V_R$：

  $$p_n(x_n)=p_{n0}\,e^{-V_R/V_T}$$

  交界處少數載子濃度**下降**，低於 $p_{n0}$。
- 此時中性區內部濃度**高於**交界處，少數載子由內部往接面擴散（與順向方向相反），電流為負。
- 推導形式相同，$V_F\to-V_R$。

**統一的電流方程式**

$$\boxed{I_{PN}=I_S\left(e^{V_{apply}/V_T}-1\right)}$$

- $V_{apply}>0$：順向偏壓
- $V_{apply}<0$：反向偏壓（$V_{apply}=-V_R$）
- 此式即二極體理想電流方程式（又稱 Shockley 方程式，此名稱為補充）。

## 7. I-V 特性曲線

**順向（$V_{apply}\gg V_T$）**：$e^{V_{apply}/V_T}\gg1$，括號中的 $-1$ 可忽略：

$$I\approx I_S\,e^{V_{apply}/V_T}$$

電流隨偏壓指數上升。例：$V_{apply}=0.5\ \text{V}$ 時 $e^{19.3}\approx2.4\times10^8$。

**反向（$-V_{apply}\gg V_T$）**：$e^{V_{apply}/V_T}\ll1$，所以括號 $\approx-1$：

$$I\approx-I_S$$

電流大小固定在 $I_S$，不再隨反向電壓增加，這就是「飽和電流」名稱的由來。例：$V_{apply}=-0.5\ \text{V}$ 時 $e^{-19.3}\approx4\times10^{-9}$。

**結論**：順向時電流呈指數上升而導通；反向時電流只有極小的 $I_S$，可視為不導通。這就是二極體「單向導通」的來源。

## 8. 總整理

| 項目 | 結論 |
|---|---|
| 反向偏壓 $V_R$ | 外加電場與內建電場同向；總電位差 $V_0+V_R$；空乏區變寬 |
| 順向偏壓 $V_F$ | 外加電場與內建電場反向；總電位差 $V_0-V_F$；空乏區變窄 |
| 寬度與電位差 | $W,\,x_p,\,x_n,\,Q_J\ \propto\ \sqrt{\text{總電位差}}$ |
| 順向注入 | 交界處少數載子 $p_n(x_n)=p_{n0}e^{V_F/V_T}$ |
| 擴散長度 | $L_p=\sqrt{D_p\tau_p}$，多餘載子以 $e^{-x/L_p}$ 下降 |
| 飽和電流 | $I_S=AQn_i^2\left(\dfrac{D_p}{L_pN_D}+\dfrac{D_n}{L_nN_A}\right)$，約 $10^{-18}\sim10^{-12}\ \text{A}$，與 $n_i^2$ 同為溫度強函式 |
| 電流方程式 | $I=I_S\left(e^{V_{apply}/V_T}-1\right)$ |
| 順向（$V\gg V_T$）| $I\approx I_Se^{V/V_T}$，指數上升 |
| 反向（$-V\gg V_T$）| $I\approx-I_S$，幾乎不導通 |

**三個最容易搞混的地方**

1. 順向電流是少數載子**注入後擴散**形成的，不是多數載子直接穿過去。
2. 括號裡的「$-1$」：順向時可忽略，反向時才是主角（讓電流變成 $-I_S$）。
3. 公式裡 $V_{apply}$ 帶正負號（順向為正、反向為負），不要跟前面的 $V_F$、$V_R$（皆為正值）混用。
