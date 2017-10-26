# Decentralized-Exchange
Smart contract for ERC 20 Token Transaction

![Decentralized Transaction](https://github.com/Luphia/Flip/blob/master/images/DecentralizedTransaction.jpg)

## Elements
- W<sub>FD</sub> 遠期交割營運錢包
- W<sub>ML</sub> 抵押貸款營運錢包
- W<sub>MT</sub> 搓合交易營運錢包
- C<sub>ER</sub> 匯率查詢合約
- C<sub>TL</sub> ERC20 Token 查詢合約
- C<sub>FD</sub> 遠期交割合約
- C<sub>ML</sub> 抵押貸款合約
- C<sub>MT</sub> 撮合交易合約
- C<sub>XPA</sub> XPA 發行合約
- C<sub>XPAUSD</sub> XPAUSD 發行合約
```
ER: Exchange Rate 匯率查詢
TL: Token List 數位貨幣清單查詢
FD: Forward Delivery 遠期交割合約
ML: Mortgage Loan 抵押貸款合約
MT: Match Trading 撮合交易合約
```

### W<sub>FD</sub>
遠期交割合約建立者錢包，負責營運遠期交割合約，並定期充值所需手續費，授權 XPA、XPAUSD 供合約操作

持有資產：
- XPA
- XPAUSD
- ETH

### W<sub>ML</sub>
抵押貸款合約建立者錢包，負責營運抵押貸款合約，並定期充值所需手續費，授權 XPA、XPAUSD 供合約操作

持有資產：
- XPA
- XPAUSD
- ETH

### W<sub>MT</sub>
撮合交易合約、數位貨幣清單查詢合約、匯率查詢合約建立者錢包，負責營運撮合交易合約，並定期充值所需手續費

持有資產：
- ETH

### C<sub>ER</sub>
- getExchangeRateBySymbol 取得貨幣兌換匯率
- updateExchangeRateBySymbol (Oracle) 更新兌換匯率

### C<sub>TL</sub>
- getAddressBySymbol 根據貨幣代碼取得智能合約地址
- setAddressBySymbol (Oracle) 設定貨幣代碼智能合約地址
- listSymbol 列出已登記的貨幣代碼
- listAddress 列出已登記的智能合約地址

### C<sub>FD</sub>
- ETH2XPA ETH 購買 XPA
- ETHBuyBack XPA 贖回 ETH
- XPAUSD2XPA XPAUSD 購買 XPA
- XPAUSDBuyBack XPA 贖回 XPAUSD
- getBuyBackRate 根據交易 ID 查詢贖回價
- getBuyBackValue 根據交易 ID 查詢可贖回總量

### C<sub>ML</sub>
- XPALoanXPAUSD XPA 抵押借貸 XPAUSD
- additionalXPALoanXPAUSD XPA 增額借貸 XPAUSD
- getLoanRate 取得借貸合約匯率
- getExchangeRage 取得即時匯率
- liquidation 清算匯率過高的借貸單
- buyBackXPA XPA 贖回

### C<sub>MT</sub>
- buyOrder 掛貨幣買單
- sellOrder 掛貨幣賣單
- cancelOrder 取消掛單
- getSellPriceByValue 根據賣單量取得最高售出單價
- getSellValueByPrice 根據賣出價取得最大匹配買單量
- getBuyPriceByValue 根據買單量取得最低買入單價
- getBuyValueByPrice 根據買入價取得最大匹配賣單量

## Reference
- https://gist.github.com/y12studio/f142cd9789c7d396d8f7
