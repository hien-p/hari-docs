---
title: A article on the anatomy of Web3
summary:  Bài viết này viết toàn cảnh về hệ sinh thái của Web3 Blockchain (my POV)
authors:
    - Harry Phan
date: 2025-07-22
some_url: https://mp.weixin.qq.com/s?__biz=MzA5OTI1NDE0Mw==&mid=2652494508&idx=1&sn=2124ff3f2f03fc0d439dfda30a1eff8e&chksm=8b6850bcbc1fd9aafcc633232ee64761c99d212716a190e05c1874419b781624906dcdaf2943&token=1958237421&lang=zh_CN#rd
extra:
  status:
    new: Recently added
---


# A article on the anatomy of Web3

Bài viết này viết toàn cảnh về hệ sinh thái của Web3 Blockchain (my POV). Web3 đến nay đã phát triển tương đối đầy đủ, hệ sinh thái cũng dần định hình rõ ràng. Nếu nhìn ở góc độ kiến trúc tổng thể hiện tại thì ta có thể chia thành các layers là blockchain network layer, middleware layer, application layer, và access layer...

Trong phần này sẽ nhắc đến khá nhiều cái tên dự án, nhưng vì dung lượng kiến thức mình có hạn nên mình sẽ không đi sâu vào từng cái mà chỉ overall.


# 1. Blockchain network layer

Ở tầng thấp nhất trong kiến trúc Web3 là lớp mạng lưới blockchain (blockchain network layer) hay còn gọi là lớp nền tảng (foundation layer). Đây chính là “cái móng nhà” của toàn bộ hệ sinh thái Web3, nơi tập hợp các blockchain khác nhau vận hành độc lập hoặc tương tác với nhau.


Hiện có rất nhiều blockchain nằm trong lớp này, có thể kể đến như: Bitcoin, Ethereum, BNB Chain (BSC), Polygon, Arbitrum, Polkadot, Cosmos, Celestia, Avalanche, Aptos, Sui và còn hàng tá cái tên khác nữa.

## 1.1 Phân tầng kiến trúc: Layer 0 / Layer 1 / Layer 2


* Layer 0 (L0): Layer 0 là lớp trừu tượng hơn, thường được gọi là lớp hạ tầng blockchain (infrastructure layer) – nơi cung cấp các dịch vụ cơ bản giúp nhiều blockchain có thể tương tác hoặc chia sẻ tài nguyên. Ví dụ: Cosmos, Polkadot,

![Layer 0 - coinbase](https://images.ctfassets.net/q5ulk4bp65r7/5w8dZBJye0z6uKpPaYD764/ef88b236609d4483917a031945e819e8/Learn_Illustration_What_are_Layer-0_protocols.jpg)
<br/>

* Layer 1 (L1): Các Layer 1 cũng chính là ví dụ điển hình cho [`“tam giác bất khả thi”`](blockchain_dilemma.md) của blockchain khó để một blockchain đồng thời đảm bảo cả 3 yếu tố: mở rộng (scalability), bảo mật (security), và phi tập trung (decentralization).

<br/>

* Layer 2 (L2): Layer 2 ra đời để giải bài toán “TPS thấp” của Layer 1, nhất là Ethereum. Layer 2 là các chuỗi phụ (subchain) nằm phía trên Layer 1, có nhiệm vụ xử lý giao dịch nhanh và rẻ hơn, sau đó gửi kết quả về Layer 1 để lưu trữ. Layer 2 giúp Layer 1 trở thành settlement layer (lớp thanh toán), còn mình thì lo phần execution layer (lớp thực thi). Một số Layer 2 nổi bật của Ethereum gồm: Arbitrum, Optimism, zkSync, StarkNet, Polygon. Bitcoin cũng có Layer 2 như: `Lightning Network`, `Stacks`, `RSK`, nhưng hiện tại vẫn chưa phổ biến bằng Ethereum.




## 1.2 Môi trường chạy smart contract

Sự phát triển của Web3 chủ yếu nhờ vào smart contract, và các smart contract cần có môi trường để chạy – gọi là virtual machine (máy ảo). Tương tự như Java cần JVM vậy.


Sau khi hiểu cấu trúc phân tầng, ta tiếp tục phân loại blockchain theo góc nhìn EVM compatibility  hay nói cách khác, blockchain đó có chạy được smart contract viết bằng Solidity và tương thích với máy ảo Ethereum hay không.

Về cơ bản, có thể chia thành hai nhóm: `EVM chains` và `Non-EVM chains`.

Hiện nay, EVM chains vẫn là dòng chủ đạo. Những blockchain này thu hút lượng lớn DApp và người dùng Web3, nhờ vào cộng đồng phát triển rộng và hệ sinh thái công cụ phong phú. Một số blockchain tương thích với EVM từ đầu như BSC, Heco, Arbitrum, Optimism, v.v. Một số khác thì phát triển sau này để tương thích, ví dụ như zkSync: phiên bản 1.0 không hỗ trợ EVM, nhưng từ 2.0 trở đi thì đã embrace EVM hoàn toàn. 


Tính đến hiện tại, phần lớn các blockchain lớn đều đã hoặc đang hỗ trợ EVM. Tuy nhiên, vẫn còn một số chuỗi nổi bật nằm ngoài hệ EVM, như Solana, Terra, NEAR, Aptos, và Sui. 

Các blockchain này thường chọn hướng đi khác biệt, cả về kiến trúc lẫn ngôn ngữ lập trình smart contract: nếu EVM chains dùng Solidity, thì các Non-EVM chains thường dùng Rust hoặc Move


> Tóm lại 

* [`EVM chains`](https://gfiblockchain.com/evm-la-gi-tai-sao-evm-la-trai-tim-cua-ethereum.html): Là những blockchain tương thích với Ethereum Virtual Machine, có thể chạy các smart contract được viết bằng Solidity. Ví dụ: Ethereum, BNB Chain, Polygon, Avalanche C-Chain…
* [`Non-EVM chains`](https://coin98.net/phan-tich-non-evm-blockchain): Không tương thích với EVM, sử dụng máy ảo riêng và thường có ngôn ngữ lập trình riêng, như: Solana (Rust/C/C++), Aptos & Sui (Move), Near protocol/ Cosmos dùng rust, Cardano dùng Haskell/Plutus..

---

## 1.3 Các vai trò trong toàn hệ sinh thái như `Tính toán` hay `Lưu trữ`

Ta cũng có thể chia blockchain theo mục tiêu sử dụng:
* Compute Chains: Tập trung vào xử lý logic và chạy smart contract.
* Storage Chains: Tập trung vào lưu trữ dữ liệu phi tập trung – ví dụ: Filecoin, Arweave, Walrus..


## 1.4 Cross-chain bridges

Mở rộng hơn là các giao thức giao tiếp giữa nhiều blockchain. Khá khó để thống kê ra số lượng bao nhiêu cross-chain được triển khai nhưng ta có những tên dẫn đầu cho phép chuyển tài sản giữa layer 2 và Ethereum một cách mược mà như `Polygon`, `Arbitrum` và `Optimism`.  Xếp sau là `Multichain` (trước đây là Anyswap) - tuy nhiên, trải qua khoảng thời gian khắc nghiệt của thị trường, cái tên Multichain đã dần phai mờ trong trí nhớ của nhiều người.



Tạm thời, đó là bức tranh tổng quan về các “thành viên” đang tạo nên lớp mạng lưới của blockchain. Tất nhiên, danh sách này sẽ còn tiếp tục thay đổi sẽ có những cái tên mới gia nhập, và cũng sẽ có những hệ sinh thái từng rầm rộ rồi dần bị lãng quên ở một góc của lịch sử Web3.

# 2. Middleware layer

Ngay phía trên lớp mạng blockchain, mình gọi đây là "middleware layer" chuyên cung cấp các dịch vụ và chức năng nền tảng cho các ứng dụng **Security audits, oracles, index query services, API services, data analysis, data storage, basic financial services, digital identities, DAO governance..**

Các thành phần trong lớp middleware này có thể là:

* On-chain protocol (chạy trực tiếp trên blockchain),
* Off-chain platform (chạy ngoài blockchain),
* Hoặc các tổ chức  centralized enterprise.


Trước tiên là về kiểm toán bảo mật (`Security Auditing`). Đây là một loại middleware cốt lõi. Vì phần lớn các blockchain và ứng dụng Web3 đều `mã nguồn mở` (open-source), và nhiều ứng dụng liên quan trực tiếp tới tài chính, nên vấn đề bảo mật trở thành ưu tiên hàng đầu, và kiểm toán bảo mật đương nhiên trở thành một nhu cầu bắt buộc. 


 Các công ty nổi tiếng trong lĩnh vực này gồm: `CertiK`, `OpenZeppelin`, `ConsenSys`, `Hacken`, `Quantstamp`; ở Trung Quốc có `SlowMist`, `ChainSec`, và `Paidun`. Ngoài ra còn có nhiều công ty/team nhiều hơn thế nữa...


Bên cạnh đó, không thể không kể tới các Bug Bounty platform như `Immunefi`, `Hacker proof`...


Tiếp theo là `Oracle`, thành phần đóng vai trò rất quan trọng trong hệ sinh thái Web3. 

Oracle là cầu nối giữa hệ thống blockchain và nguồn dữ liệu bên ngoài, giúp thực hiện việc giao tiếp dữ liệu giữa smart contract và thế giới thực. Vì bản thân mạng lưới blockchain bị giới hạn bởi tính nhất quán trạng thái (`state consistency`), nên để đảm bảo rằng mỗi node đều cho ra cùng một kết quả khi nhận cùng một input, blockchain được thiết kế như một hệ thống đóng, chỉ có thể lấy dữ liệu nội bộ (on-chain), không thể chủ động lấy dữ liệu từ bên ngoài (off-chain). 

Tuy nhiên, trong nhiều tình huống ứng dụng, dữ liệu bên ngoài là bắt buộc và chúng được cung cấp thông qua `oracle`. Đây cũng là cách duy nhất để blockchain có thể tương tác với dữ liệu ngoài chuỗi.

Các loại oracle hiện nay có thể chia thành: oracle cho DeFi, NFT, SocialFi, oracle cross-chain, oracle bảo mật riêng tư, oracle tín dụng, và mạng lưới oracle phi tập trung. Một số dự án oracle tiêu biểu gồm: CreDA, Privy, UMA, Banksea, DOS, NEST, Chainlink, v.v. Trong đó, Chainlink là dự án dẫn đầu mảng oracle, được định vị là một mạng lưới oracle phi tập trung, cung cấp nhiều sản phẩm như: Data Feeds, VRF, Keepers, Proof of Reserve, CCIP,…


Tiếp theo là  truy vấn dữ liệu (`Index Query`), một middleware quan trọng giúp giải quyết bài toán truy vấn dữ liệu on-chain phức tạp. Ví dụ, nếu muốn truy vấn tổng khối lượng giao dịch trên Uniswap trong một ngày cụ thể, thì việc truy vấn trực tiếp từ blockchain là rất khó khăn. Do đó, cần có các dịch vụ truy vấn chỉ mục, với những đại diện chính là The Graph và Covalent. The Graph hoạt động bằng cách giám sát dữ liệu on-chain và chuyển hóa chúng thành dữ liệu tùy chỉnh để lưu trữ và truy vấn. Trong khi đó, Covalent đóng gói các dữ liệu phổ biến và thường dùng thành các API thống nhất để người dùng dễ truy vấn.


---

Khi nói đến dịch vụ API, ngoài Covalent, còn có nhiều nhà cung cấp API phục vụ các mục đích khác nhau, ví dụ:
* NFTScan: chuyên cung cấp dữ liệu API về NFT,
* Infura và Alchemy: cung cấp dịch vụ node cho blockchain.

---
**Data analytics** cũng là một thành phần middleware liên quan tới dữ liệu. Bạn có thể từng nghe như `Dune Analytics`, `Flipside Crypto`, `DeBank`, `Chainalysis`. 

--- 
Tiếp theo là middleware cung cấp các **defi service**. Các giao thức tiêu biểu gồm: `Uniswap`, `Curve`, `Compound`, `Aave`, v.v.
	•	Uniswap và Curve là các giao thức giao dịch (DEX),
	•	Compound và Aave là các giao thức cho vay (lending).

Về bản chất, đây là các giao thức ở lớp ứng dụng (application layer), nhưng vì ngày càng có nhiều ứng dụng khác dựa vào chúng như một thành phần cơ bản để xây dựng, nên chúng trở thành các giao thức dùng chung, tương tự như các khối Lego từ đó đảm nhận vai trò của middleware.

⸻

Trên thực tế, bất kỳ thành phần có thể tái sử dụng (composable) nào  dù là giao thức on-chain, dịch vụ off-chain do thực thể tập trung cung cấp, hoặc tổ chức `DAO` đều có thể được phân loại vào “lớp middleware”, miễn là dịch vụ mà nó cung cấp được đa số ứng dụng khác cần sử dụng.

# 3. Application Layer

Đây là tầng sôi động và phong phú nhất trong hệ sinh thái Web3. Tại đây, hàng loạt dApp (decentralized applications) được phát triển, mỗi ứng dụng đại diện cho một hướng đi riêng. Mình dùng từ "Bách hoa đua nở, bách gia tranh minh" trong web3 hiện tại 🤣.


Trong phần này, mình sẽ đi qua domain tiêu biểu và đang phát triển mạnh trong Application Layer

## 3.1 NFT (Non-Fungible Token)

NFT là viết tắt của Non-Fungible Token — tức token không thể thay thế. Chúng ta thường gọi NFT là các tài sản kỹ thuật số. NFT đại diện cho tài sản số độc nhất, chẳng hạn như tác phẩm nghệ thuật, nhân vật game, hay vật phẩm sưu tầm.


Dự án NFT thực sự đầu tiên là **CryptoPunks**, ra mắt vào tháng 6 năm 2017. Bộ sưu tập này gồm **10.000 hình đại diện pixel kích thước 24x24**, được tạo ra bằng thuật toán, mỗi hình là một cá thể độc lập, không trùng lặp. Hình dưới đây là ví dụ một số avatar hiển thị trên trang web chính thức của CryptoPunks:

![](https://img.learnblockchain.cn/attachments/2023/01/qwP3dC5S63d32dfba882c.png)

Bạn cũng có thể vào [`OpenSea`](https://opensea.io/collection/cryptopunks) để xem chi tiết nhé. Ở thời điểm mình viết bài này thì gía sàn(floor price) là 49.99 ETH (tương đương 185,000 USD tính theo giá hiện tại). Giao dịch đắt nhất từng được ghi nhận là **8,000 ETH** vào ngày 12/02/2022.

Bạn sẽ thắc mắc là  vì sao một hình đại diện pixel có thể đắt như vậy?

Một trong những lý do chính là tính tiên phong. CryptoPunks là dự án NFT đầu tiên trên Ethereum, tương tự như cách Bitcoin là blockchain đầu tiên, điều này mang lại giá trị biểu tượng và sưu tầm lớn.


Lấy cảm hứng từ `CryptoPunks`, studio Axiom Zen (sau này là Dapper Labs) ra mắt CryptoKitties vào cuối năm 2017. Dự án nhanh chóng gây sốt, đến mức làm tắc nghẽn mạng Ethereum  từ đó bộc lộ rõ các vấn đề hiệu năng.

Ngay trước khi phát hành, `Dieter Shirley`, CTO của Axiom Zen, đã đề xuất chuẩn ERC-721 là  chuẩn kỹ thuật giúp chuẩn hóa các token không thể thay thế (NFT). Sự thành công của CryptoKitties đã đẩy nhanh việc phổ biến của chuẩn này, và ngày nay ERC-721 đã trở thành tiêu chuẩn cơ bản của NFT trên EVM.

---
###  Các lĩnh vực ứng dụng chính của NFT

NFT đã mở rộng ra nhiều lĩnh vực trong thế giới số. Nếu phân loại theo ứng dụng, có thể chia ra các nhóm tiêu biểu sau:

* Sưu tầm (Collectibles): Sưu tầm là lĩnh vực NFT phát triển đầu tiên, với đặc điểm cốt lõi là tính khan hiếm. Ví dụ, trong 10,000 CryptoPunks thì “Alien” cực hiếm → giá cao còn “Male” phổ biến hơn → giá thấp hơn
* Nghệ thuật(artworks): NFT giúp nghệ sĩ bảo vệ bản quyền và sở hữu tác phẩm. 
* Music: NFT giúp nhạc sĩ kiểm soát bản quyền và doanh thu:
* film: Nhiều thương hiệu phim lớn phát hành NFT như **Game of Thrones, Matrix, Batman, Lord of the Rings, The Walking Dead**
* Gaming: NFT đóng vai trò là tài sản trong game — giúp người chơi thực sự sở hữu vật phẩm và có thể giao dịch bên ngoài
* Virtual Land: Đất ảo là thành phần quan trọng trong metavers với các dự án lớn: Decentraland, The Sandbox, Otherside, Axie Land, Roblox...
* NFT x DeFi: NFT có thể bị phân mảnh trở thành token có thể giao dịch, staking, lending…
* Brand: NFT như một hình thức marketing và kích thích cho cộng đồng. Các thương hiệu lớn đã tham gia như Gucci, LV, Hermes, Starbucks, [Taco Bell, Coca-Cola, Pizza Hut](https://foodinstitute.com/focus/rock-the-blockchain-nfts-in-food-and-beverage/)
* DID: DID là hạ tầng cho danh tính Web3. Ví dụ ENS (Ethereum Name Service) giống như “DNS” cho Web3

**Ứng dụng của NFT thì nhiều vô kể, mấy nhóm trên chỉ là phần nổi của tảng băng**. Vì NFT mang tính đại diện cho quyền sở hữu, nên gần như bất cứ thứ gì "có owner" đều có thể được mã hóa thành NFT. Vậy nên trong cộng đồng mới có câu: *everything can be NFT* nghĩa là cái gì cũng có thể NFT hóa được hết á!


## 3.2 DeFi

DeFi viết tắt của Decentralized Finance (tài chính phi tập trung)  chính thức bùng nổ vào mùa hè năm 2020, tới mức người ta đặt hẳn cái tên riêng cho giai đoạn này là “DeFi Summer” 🌞. 

Theo số liệu từ TradingView, khi mới xuất hiện, tổng giá trị thị trường của DeFi chỉ khoảng 5 tỷ USD, nhưng sau đó thì leo dốc không phanh, chạm đỉnh vào cuối năm 2021 với [gần 180 tỷ USD](https://www.investmentexecutive.com/news/research-and-markets/defi-poses-little-threat-to-traditional-finance-fitch/)



Bản thân Defi là một hệ sinh thái lớn với nhiều “sub-sector” khác nhau như: **stablecoins, DEX, derivatives, lending, aggregators, insurance, prediction markets, index…**

### 3.2.1 Stablecoin 

Stablecoin là “đồng tiền ổn định” ví dụ USD trên Web3. Có thể chia làm 3 loại chính:

* Centralized Stablecoins: do tổ chức tập trung phát hành, backing bằng fiat thật, kiểu 1 USDT = 1 USD. Tiêu biểu có **USDT (Tether), USDC (Circle), và BUSD (Binance + Paxos)**. Tuy tập trung, nhưng hiện vẫn là dòng stablecoin thanh khoản cao nhất thị trường.

* Overcollateralized Stablecoins: loại này được đúc bằng cách thế chấp crypto khác, thường dùng smart contract và oracle để đảm bảo peg 1:1. Đại diện tiêu biểu là **DAI** từ MakerDAO có decentralization cao, nhưng phải thế chấp nhiều hơn giá trị cần mint.

* Algorithmic Stablecoins:  không cần thế chấp mà dùng thuật toán để cân bằng cung – cầu. Có hàng loạt tên tuổi từng thử như UST, FEI, FRAX, CUSD, USDD…


### 3.2.2 DEX (Decentralized Exchange)

DEX (Decentralized Exchange) chính là nơi giao dịch tài sản crypto không cần trung gian. Đây là sector có market cap to nhất trong DeFi, và cũng là cái nôi cho đủ kiểu mô hình giao dịch như:

* **Spot DEX** vs **Derivatives DEX**
* **Orderbook mode** vs **AMM mode**


Về **Orderbook DEX** thì giống sàn chứng khoán truyền thống. Người dùng đặt lệnh mua/bán. Có 3 kiểu triển khai:

* On-chain Orderbook: như EtherDelta, cực phi tập trung nhưng chậm & phí cao.
* Off-chain match, on-chain settle: như 0x protocol, tiết kiệm gas hơn nhưng vẫn phải settle từng giao dịch
* Layer2 Orderbook: như dYdX dùng StarkEx – trade mượt như CEX nhưng vẫn giữ tính phi tập trung ở mức vừa phải.


Về **AMM DEX**, AMM (Automated Market Maker) là cú bùng nổ thật sự của DEX. Khởi nguồn từ **Uniswap**, rồi lan ra **SushiSwap, Curve, Balancer, GMX…**. Mô hình này dựa trên liquidity pool, người dùng bơm tài sản vào pool để trở thành LP, đổi lại nhận fee từ người trade. Tức là bạn vừa làm trader, vừa làm ngân hàng luôn. 


Về Derivatives, là đòn bẩy thì trong DeFi gồm 4 nhóm chính:

* Perpetual contracts: giống futures, có leverage. Dẫn đầu là dYdX, apeX, GMX, Perpetual Protocol.
* Options: phức tạp hơn future, ít phổ biến. Có Hegic, Opyn, Charm, Primitive…
* Synthetic Assets: tạo tài sản mô phỏng như vàng, cổ phiếu… Tiêu biểu là Synthetix, UMA, Mirror, Duet.
* Interest Rate Derivatives: như BarnBridge, Swivel, cho phép user “đặt cược” vào lãi suất crypto.


Về **Lendind**, cho vay là nền tảng thứ hai bên cạnh DEX. Các ông lớn gồm **Compound, Aave, Maker, Cream, Liquity, Venus, Euler, Fuse…** Chủ yếu dùng mô hình **over-collateralized**: muốn vay $80 thì phải bạn cắm ít nhất $100 tài sản điều này nhằm bảo vệ cả borrower lẫn protocol.

Ngoài ra còn có:

* **Interest-free loan**: như Liquity, vay không lãi, chỉ trả 1 lần phí upfront.
* **Asset isolation pools**: tách các pool ra 
* **Cross-chain lending**: với các tên như Flux, Aave, Compound mở rộng sang nhiều chain.
* **Credit-based loan**: như Wing Finance, nhưng vẫn thiếu hệ thống on-chain credit chuẩn chỉnh.

Về Aggregator, bạn sẽ thắc mắc nếu có rất nhiều protocol thì làm sao để ta có thể quản lý thì  Aggregator là công cụ gom tụ mọi thứ lại:

* **DEX Aggregator**: tìm giá tốt nhất từ nhiều DEX → 1inch, Matcha, ParaSwap, MetaMask Swap.
* **Yield Aggregator**: tự động yield farming → Yearn Finance, Alpha Finance, Harvest, Convex
* **Asset Management**: quản lý danh mục & portfolio → Zapper, Zerion.
* **Data Aggregator**: như CoinMarketCap, DeFi Pulse, DeBank – dù là centralized nhưng vẫn cực quan trọng.

Về **Insurance**, một số cái tên tiên phong gồm: Nexus Mutual, Cover, Unslashed, Opium…


Về **Prediction Markets**, dự đoán kết quả bầu cử, giá crypto, hay bất cứ sự kiện nào,dự đoán là playground cho ai muốn predict bằng dữ liệu. 

Ngoài ra ta còn có ETF phiên bản web3, nghĩa là thay vì pick một token thì bạn có thể hold nhiều token. Một số chỉ số nổi bật ta nên biết như **DPI, sDEFI, PIPT, DEFI++, BCP...**


DeFi là nơi rebuild lại từ đầu, bằng smart contract, phi tập trung, permissionless. Mỗi mảnh ghép mà mình kể trên đều đóng vai trò riêng và khi xâu chuỗi lại, nó tạo nên hệ sinh thái lớn.

## 3.3 GameFi 

GameFi là viết tắt của Game Finance tức là game + tài chính. Nói cách khác, đây chính là thuật ngữ cool ngầu hơn của Web3 games. 

Trước khi cái tên GameFi xuất hiện, người ta thường gọi mấy trò này là blockchain games hay chain games. 

Như đề cập trong nội dung NFT, Dự án tiên phong phải kể đến là CryptoKitties là trò nuôi mèo ảo từng làm tắc nghẽn cả mạng Ethereum hồi 2017. 

Mỗi chú mèo là một NFT độc lập, có gen, có ngoại hình riêng. Người chơi mua mèo, rồi “phối giống” để đẻ ra mèo con cũng là NFT mới. Mèo nào gen hiếm thì giá càng chát. Tính đến cuối tháng 1/2023, đã có hơn 2 triệu mèo được “mint”, với hơn **136,000** ví đang giữ mèo. Sau CryptoKitties là loạt clone sinh sản như **CryptoRabbit, CryptoFrog, CryptoDongle**…  

Hoặc một game xổ số tên **Fomo3D** dùng ETH.  Cứ mua Key là nhận được cổ tức. Ai là người cuối cùng mua Key trước khi countdown kết thúc (24h) thì sẽ jackpot. Nhưng mỗi lần ai đó mua Key mới, thời gian sẽ cộng thêm 30s.


Nói đến gamefi, mình không thể nào không kể đến là **Axie Infinity**. Ra mắt từ 2018, nhưng phải đến 2021 mới “nổ tung” với mô hình Play-to-Earn (P2E). Trong game, bạn sắm vài con *Axie* (kiểu Pokémon NFT), sau đó đem đi đánh nhau, breed (phối giống), trade trên marketplace. 

Chiến thắng sẽ nhận được SLP token, dùng SLP + AXS để đúc Axie mới → bán lấy lời → quy đổi thành ETH hoặc stablecoin, rồi rút về ví. **Axie Infinity** tạo ra một làn sóng lớn giúp gamefi bùng nổ ở thời điểm 2021. 

Sau Axie, mô hình chơi để kiếm (P2E) gần như trở thành tiêu chuẩn cho Web3 games. **“tokenomics”, “earn model”, “NFT assets”** sẽ là tiêu chuẩn để mọi người đánh giá. 

## 3.4 SocialFi

SocialFi là viết tắt của Social + Finance. Hiểu đơn giản là mạng xã hội phiên bản Web3 phi tập trung, tích hợp tài chính, và cho phép người dùng kiếm tiền từ tương tác xã hội. Khái niệm này chỉ thực sự hot trong 1–2 năm trở lại đây.

Hầu hết các nền tảng SocialFi ngày nay đều vận hành theo mô hình quản trị DAO (Decentralized Autonomous Organization) tức cộng đồng là người đưa ra quyết định.

Khác với memecoin, thì socialfi sẽ có tính thực tế hơn và có thể scale được. Tuy nhiên để build một dapp Socialfi thì technical có rất nhiều thử thách và builder phải có tìm những câu trả lời phù hợp. Bởi vì khác với việc xử lý data ở web2 như Facebook, X khi mà mỗi ngày generate hàng tỷ interactions thì liệu mỗi post/comment trên socialfi có thể là on chain transaction được ko? 

Thứ 2 là Người dùng Web2 đã quen với mô hình như subcription (Patreon, Substack), Donate cho creator (Ko-fi, BuyMeACoffee)... SocialFi muốn bắt chước mô hình này thì phải build tools đủ đơn giản, nhưng vẫn an toàn để người dùng setup .


# 4. Access Layer

Đây là tầng trên cùng của kiến trúc Web3 nơi user như bạn và mình thực sự tương tác blockchain. Các access layer chính là: **wallets, browsers, aggregators, và cả… Twitter nữa**.

Đầu tiên là **Wallet**: Đây là entry point quan trọng nhất. Không có ví bạn sẽ không thể tương tác với Blockchain. Hiện tại có các loại ví như: 
* Browser Wallets: Metamask, Coinbase Wallet, WalletConnect...
* Mobile Wallets: Ví nổi bậ MetaMask Mobile, Coinbase Wallet, TokenPocket, Rainbow, BitKeep, Crypto.com, imToken… Và cũng có nhiều ví hỗ trợ đa chain như BTC, ETH, BNB Chain, Polygon, Solana, Aptos, Cosmos…
* Hardware Wallets: Lưu private key riêng trong thiết bị vật lý offline. Nổi bật như Ledger (Nano X, Nano S Plus, Ledger Stax), Trezor (Model One, Model T)
* Multi-Signature Wallet: dành cho ví cần nhiều người ký dùng set cấu hình 2/3 người ký thì mới thực hiện giao dịch. Dùng nhiều trong DAO hoặc team để tránh mất tiền oan.
*  MPC Wallet: MPC = Multi-Party Computation. Ví chia nhỏ private key thành nhiều mảnh, mỗi bên giữ một phần. khi ký, mới “ghép lại” đủ mảnh để unlock. Gần giống multi-sig nhưng chạy off-chain, không cần smart contract.
* Smart Contract Wallet + Account Abstraction


Các browsers: Hầu hết các DApp hiện vẫn là web app, nên trình duyệt đóng vai trò quan trọng trong việc render UI và kết nối với ví. Chrome là browser phổ biến nhất vì mọi browser extension wallet đều support. Tiếp đến ta có như Brave ( có sẵn Brave wallet)

Nhiều nền tảng như Twitter (X), Reddit… là nơi mà crypto culture diễn ra với các Cộng đồng NFT, DAO, memecoin... 
