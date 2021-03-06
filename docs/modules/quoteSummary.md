# quoteSummary

Note: in the original `node-yahoo-finance`, we incorrectly called this
"`quote`".  See the [quote](./quote.md) docs, for this similar but
different module.

## Usage:

```js
import yahooFinance from 'yahoo-finance2';

const symbol = 'OCDO.L';
const queryOptions = { modules: ['price', 'summaryDetail'] }; // defaults
const result = await yahooFinance.quoteSummary(symbol, queryOptions);

{
  summaryDetail: {
    maxAge: 1,
    priceHint: 2,
    previousClose: 2828,
    open: 2843,
    dayLow: 2776,
    dayHigh: 2853,
    regularMarketPreviousClose: 2828,
    regularMarketOpen: 2843,
    regularMarketDayLow: 2776,
    regularMarketDayHigh: 2853,
    payoutRatio: 0,
    beta: 0.693054,
    volume: 1004034,
    regularMarketVolume: 1004034,
    averageVolume: 1831257,
    averageVolume10days: 2115356,
    averageDailyVolume10Day: 2115356,
    bid: 2788,
    ask: 2790,
    bidSize: 0,
    askSize: 0,
    marketCap: 20966455296,
    fiftyTwoWeekLow: 994.012,
    fiftyTwoWeekHigh: 2914,
    priceToSalesTrailing12Months: 10.691171,
    fiftyDayAverage: 2477.3635,
    twoHundredDayAverage: 2397.2805,
    currency: 'GBp',
    fromCurrency: null,
    toCurrency: null,
    lastMarket: null,
    algorithm: null,
    tradeable: false
  },
  price: {
    maxAge: 1,
    regularMarketChangePercent: -0.00990099,
    regularMarketChange: -28,
    regularMarketTime: new Date("2021-02-02T16:35:44.000Z"),
    priceHint: 2,
    regularMarketPrice: 2800,
    regularMarketDayHigh: 2853,
    regularMarketDayLow: 2776,
    regularMarketVolume: 1004034,
    averageDailyVolume10Day: 2115356,
    averageDailyVolume3Month: 1831257,
    regularMarketPreviousClose: 2828,
    regularMarketSource: 'DELAYED',
    regularMarketOpen: 2843,
    exchange: 'LSE',
    exchangeName: 'LSE',
    exchangeDataDelayedBy: 20,
    marketState: 'PREPRE',
    quoteType: 'EQUITY',
    symbol: 'OCDO.L',
    underlyingSymbol: null,
    shortName: 'OCADO GROUP PLC ORD 2P',
    longName: 'Ocado Group plc',
    currency: 'GBp',
    quoteSourceName: 'Delayed Quote',
    currencySymbol: '£',
    fromCurrency: null,
    toCurrency: null,
    lastMarket: null,
    marketCap: 20966455296
  }
}
```

## API

```js
await yahooFinance.quoteSummary(symbol, queryOptions, moduleOptions);
```

### Symbol

Symbol name as used by Yahoo (often the stock ticker).  You can find it
using [autoc](./auto.md) or [search](./search.md).

### Module Options

See [Common Options](../README.md#common-options).

### Query Options

| Name          | Type      | Default    | Description                       |
| ------------- | ----------| ---------- | --------------------------------- |
| `modules`     | `Array<string>`  | `["price","summaryDetail"]` | List of modules to query


The full list of submodules and their output:

* [assetProfile](#assetProfile)
* [balanceSheetHistory](#balanceSheetHistory)
* [balanceSheetHistoryQuarterly](#balanceSheetHistoryQuarterly)
* [calendarEvents](#calendarEvents)
* [cashflowStatementHistory](#cashflowStatementHistory)
* [cashflowStatementHistoryQuarterly](#cashflowStatementHistoryQuarterly)
* [defaultKeyStatistics](#defaultKeyStatistics)
* [earnings](#earnings)
* [earningsHistory](#earningsHistory)
* [earningsTrend](#earningsTrend)
* [financialData](#financialData)
* [fundOwnership](#fundOwnership)
* [fundPerformance](#fundPerformance)
* [fundProfile](#fundProfile)
* [incomeStatementHistory](#incomeStatementHistory)
* [incomeStatementHistoryQuarterly](#incomeStatementHistoryQuarterly)
* [indexTrend](#indexTrend)
* [industryTrend](#industryTrend)
* [insiderHolders](#insiderHolders)
* [insiderTransactions](#insiderTransactions)
* [institutionOwnership](#institutionOwnership)
* [majorDirectHolders](#majorDirectHolders)
* [majorHoldersBreakdown](#majorHoldersBreakdown)
* [netSharePurchaseActivity](#netSharePurchaseActivity)
* [price](#price)
* [quoteType](#quoteType)
* [recommendationTrend](#recommendationTrend)
* [secFilings](#secFilings)
* [sectorTrend](#sectorTrend)
* [summaryDetail](#summaryDetail)
* [summaryProfile](#summaryProfile)
* [symbol](#symbol)
* [topHoldings](#topHoldings)
* [upgradeDowngradeHistory](#upgradeDowngradeHistory)

<a name="assetProfile"></a>
### assetProfile

```js
await yahooFinance.quoteSummary('AAPL', { modules: [ "assetProfile" ] });

{
  assetProfile: {
    address1: 'One Apple Park Way',
    city: 'Cupertino',
    state: 'CA',
    zip: '95014',
    country: 'United States',
    phone: '408-996-1010',
    website: 'http://www.apple.com',
    industry: 'Consumer Electronics',
    sector: 'Technology',
    longBusinessSummary: 'Apple Inc. designs, manufactures, and markets smartphones, personal computers, tablets, wearables, and accessories worldwide. It also sells various related services. The company offers iPhone, a line of smartphones; Mac, a line of personal computers; iPad, a line of multi-purpose tablets; and wearables, home, and accessories comprising AirPods, Apple TV, Apple Watch, Beats products, HomePod, iPod touch, and other Apple-branded and third-party accessories. It also provides AppleCare support services; cloud services store services; and operates various platforms, including the App Store, that allow customers to discover and download applications and digital content, such as books, music, video, games, and podcasts. In addition, the company offers various services, such as Apple Arcade, a game subscription service; Apple Music, which offers users a curated listening experience with on-demand radio stations; Apple News+, a subscription news and magazine service; Apple TV+, which offers exclusive original content; Apple Card, a co-branded credit card; and Apple Pay, a cashless payment service, as well as licenses its intellectual property. The company serves consumers, and small and mid-sized businesses; and the education, enterprise, and government markets. It sells and delivers third-party applications for its products through the App Store. The company also sells its products through its retail and online stores, and direct sales force; and third-party cellular network carriers, wholesalers, retailers, and resellers. Apple Inc. was founded in 1977 and is headquartered in Cupertino, California.',
    fullTimeEmployees: 147000,
    companyOfficers: [
      {
        maxAge: 1,
        name: 'Mr. Timothy D. Cook',
        age: 59,
        title: 'CEO & Director',
        yearBorn: 1961,
        fiscalYear: 2020,
        totalPay: 14769259,
        exercisedValue: 0,
        unexercisedValue: 0
      },
      /* ... */
    ],
    auditRisk: 1,
    boardRisk: 1,
    compensationRisk: 3,
    shareHolderRightsRisk: 1,
    overallRisk: 1,
    governanceEpochDate: new Date("2021-01-22T00:00:00.000Z"),
    compensationAsOfEpochDate: new Date("2020-12-31T00:00:00.000Z"),
    maxAge: 86400
  }
}
```

<a name="balanceSheetHistory"></a>
### balanceSheetHistory

```js
await yahooFinance.quoteSummary('BABA', { modules: [ "balanceSheetHistory" ] });

{
  balanceSheetHistory: {
    balanceSheetStatements: [
      {
        maxAge: 1,
        endDate: new Date("2020-03-31T00:00:00.000Z"),
        cash: 330503000000,
        shortTermInvestments: 32712000000,
        netReceivables: 43625000000,
        inventory: 14859000000,
        otherCurrentAssets: 33677000000,
        totalCurrentAssets: 462923000000,
        longTermInvestments: 350961000000,
        propertyPlantEquipment: 138047000000,
        goodWill: 276782000000,
        intangibleAssets: 60947000000,
        otherAssets: 23325000000,
        deferredLongTermAssetCharges: 7590000000,
        totalAssets: 1312985000000,
        accountsPayable: 67173000000,
        otherCurrentLiab: 141395000000,
        longTermDebt: 120276000000,
        otherLiab: 61198000000,
        deferredLongTermLiab: 275000000,
        minorityInterest: 115147000000,
        totalCurrentLiabilities: 241872000000,
        totalLiab: 442437000000,
        commonStock: 1000000,
        retainedEarnings: 412387000000,
        treasuryStock: -694000000,
        capitalSurplus: 343707000000,
        otherStockholderEquity: -694000000,
        totalStockholderEquity: 755401000000,
        netTangibleAssets: 417672000000
      },
      /* ... */
    ],
    maxAge: 86400
  }
}
```

<a name="balanceSheetHistoryQuarterly"></a>
### balanceSheetHistoryQuarterly

```js
await yahooFinance.quoteSummary('BIDU', { modules: [ "balanceSheetHistoryQuarterly" ] });

{
  balanceSheetHistoryQuarterly: {
    balanceSheetStatements: [
      {
        maxAge: 1,
        endDate: new Date("2020-09-30T00:00:00.000Z"),
        cash: 18423000000,
        shortTermInvestments: 126876000000,
        netReceivables: 8353000000,
        otherCurrentAssets: 9500000000,
        totalCurrentAssets: 163152000000,
        longTermInvestments: 81289000000,
        propertyPlantEquipment: 26802000000,
        goodWill: 21776000000,
        intangibleAssets: 8095000000,
        otherAssets: 13628000000,
        deferredLongTermAssetCharges: 804000000,
        totalAssets: 314742000000,
        accountsPayable: 31592000000,
        shortLongTermDebt: 7506000000,
        otherCurrentLiab: 14095000000,
        longTermDebt: 56852000000,
        otherLiab: 7990000000,
        deferredLongTermLiab: 5517000000,
        minorityInterest: 7369000000,
        totalCurrentLiabilities: 61633000000,
        totalLiab: 131082000000,
        commonStock: 176291000000,
        totalStockholderEquity: 176291000000,
        netTangibleAssets: 146420000000
      },
      /* ... */
    ],
    maxAge: 86400
  }
}

```

<a name="calendarEvents"></a>
### calendarEvents

```js
await yahooFinance.quoteSummary('WMT', { modules: [ "calendarEvents" ] });

{
  calendarEvents: {
    maxAge: 1,
    earnings: {
      earningsDate: [ new Date("2021-02-18T00:00:00.000Z") ],
      earningsAverage: 1.5,
      earningsLow: 1.4,
      earningsHigh: 1.82,
      revenueAverage: 148000000000,
      revenueLow: 144853000000,
      revenueHigh: 150666000000
    },
    exDividendDate: new Date("2020-12-10T00:00:00.000Z"),
    dividendDate: new Date("2021-01-04T00:00:00.000Z")
  }
}

```

<a name="cashflowStatementHistory"></a>
### cashflowStatementHistory

```js
await yahooFinance.quoteSummary('KO', { modules: [ "cashflowStatementHistory" ] });

{
  cashflowStatementHistory: {
    cashflowStatements: [
      {
        maxAge: 1,
        endDate: new Date("2019-12-31T00:00:00.000Z"),
        netIncome: 8920000000,
        depreciation: 1365000000,
        changeToNetincome: -180000000,
        changeToAccountReceivables: -158000000,
        changeToLiabilities: 1318000000,
        changeToInventory: -183000000,
        changeToOperatingActivities: -707000000,
        totalCashFromOperatingActivities: 10471000000,
        capitalExpenditures: -2054000000,
        investments: 2269000000,
        otherCashflowsFromInvestingActivities: -56000000,
        totalCashflowsFromInvestingActivities: -3976000000,
        dividendsPaid: -6845000000,
        netBorrowings: -1841000000,
        otherCashflowsFromFinancingActivities: -227000000,
        totalCashFromFinancingActivities: -9004000000,
        effectOfExchangeRate: -72000000,
        changeInCash: -2581000000,
        repurchaseOfStock: -1103000000,
        issuanceOfStock: 1012000000
      },
      /* ... */
    ],
    maxAge: 86400
  }
}
```

<a name="cashflowStatementHistoryQuarterly"></a>
### cashflowStatementHistoryQuarterly

```js
await yahooFinance.quoteSummary('PFE', { modules: [ "cashflowStatementHistoryQuarterly" ] });


```

<a name="defaultKeyStatistics"></a>
### defaultKeyStatistics

```js
await yahooFinance.quoteSummary('', { modules: [ "defaultKeyStatistics" ] });

{
  cashflowStatementHistoryQuarterly: {
    cashflowStatements: [
      {
        maxAge: 1,
        endDate: 2020-09-27T00:00:00.000Z,
        netIncome: 2194000000,
        depreciation: 1258000000,
        changeToNetincome: -511000000,
        changeToLiabilities: 0,
        changeToOperatingActivities: -851000000,
        totalCashFromOperatingActivities: 2090000000,
        capitalExpenditures: -525000000,
        investments: 838000000,
        otherCashflowsFromInvestingActivities: 173000000,
        totalCashflowsFromInvestingActivities: 481000000,
        netBorrowings: -618000000,
        otherCashflowsFromFinancingActivities: -2251000000,
        totalCashFromFinancingActivities: -2821000000,
        effectOfExchangeRate: 31000000,
        changeInCash: -218000000,
        issuanceOfStock: 48000000
      },
      /* ... */
    ],
    maxAge: 86400
  }
}

```

<a name="earnings"></a>
### earnings

```js
await yahooFinance.quoteSummary('AAPL', { modules: [ "earnings" ] });

{
  earnings: {
    maxAge: 86400,
    earningsChart: {
      quarterly: [
        { date: '1Q2020', actual: 0.64, estimate: 0.56 },
        { date: '2Q2020', actual: 0.64, estimate: 0.51 },
        { date: '3Q2020', actual: 0.73, estimate: 0.7 },
        { date: '4Q2020', actual: 1.68, estimate: 1.41 }
      ],
      currentQuarterEstimate: 0.98,
      currentQuarterEstimateDate: '1Q',
      currentQuarterEstimateYear: 2021,
      earningsDate: [
        new Date("2021-04-28T00:00:00.000Z"),
        new Date("2021-05-03T00:00:00.000Z")
      ]
    },
    financialsChart: {
      yearly: [
        { date: 2017, revenue: 229234000000, earnings: 48351000000 },
        { date: 2018, revenue: 265595000000, earnings: 59531000000 },
        { date: 2019, revenue: 260174000000, earnings: 55256000000 },
        { date: 2020, revenue: 274515000000, earnings: 57411000000 }
      ],
      quarterly: [
        { date: '1Q2020', revenue: 58313000000, earnings: 11249000000 },
        { date: '2Q2020', revenue: 59685000000, earnings: 11253000000 },
        { date: '3Q2020', revenue: 64698000000, earnings: 12673000000 },
        {
          date: '4Q2020',
          revenue: 111439000000,
          earnings: 28755000000
        }
      ]
    },
    financialCurrency: 'USD'
  }
}
```

<a name="earningsHistory"></a>
### earningsHistory

```js
await yahooFinance.quoteSummary('MSFT', { modules: [ "earningsHistory" ] });

{
  earningsHistory: {
    history: [
      {
        maxAge: 1,
        epsActual: 1.4,
        epsEstimate: 1.26,
        epsDifference: 0.14,
        surprisePercent: 0.111,
        quarter: 1585612800,
        period: '-4q' // "-3q", "-2q", "-1q"
      },
      /* ... */
    ],
    maxAge: 86400
  }
}
```

<a name="earningsTrend"></a>
### earningsTrend

```js
await yahooFinance.quoteSummary('AMZN', { modules: [ "earningsTrend" ] });

{
  earningsTrend: {
    trend: [
      {
        maxAge: 1,
        period: '0q', // "+1q", "0y", "+1y", "+5y", "-5y"
        endDate: new Date("2021-03-31T00:00:00.000Z"),
        growth: 0.81,
        earningsEstimate: {
          avg: 9.07,
          low: 5.91,
          high: 11.58,
          yearAgoEps: 5.01,
          numberOfAnalysts: 30,
          growth: 0.81
        },
        revenueEstimate: {
          avg: 95686100000,
          low: 89547000000,
          high: 101178000000,
          numberOfAnalysts: 31,
          yearAgoRevenue: 75452000000,
          growth: 0.268
        },
        epsTrend: {
          current: 9.07,
          '7daysAgo': 9.04,
          '30daysAgo': 9.22,
          '60daysAgo': 9.2,
          '90daysAgo': 9.23
        },
        epsRevisions: {
          upLast7days: 2,
          upLast30days: 5,
          downLast30days: 1,
          downLast90days: {}
        }
      },
      /* ... */
    ],
    maxAge: 1
  }
}

```

<a name="financialData"></a>
### financialData

```js
await yahooFinance.quoteSummary('TSLA', { modules: [ "financialData" ] });

{
  financialData: {
    maxAge: 86400,
    currentPrice: 872.79,
    targetHighPrice: 1200,
    targetLowPrice: 67,
    targetMeanPrice: 580.38,
    targetMedianPrice: 545,
    recommendationMean: 2.9,
    recommendationKey: 'hold',
    numberOfAnalystOpinions: 29,
    totalCash: 14531000320,
    totalCashPerShare: 15.33,
    ebitda: 4019000064,
    totalDebt: 15162999808,
    quickRatio: 1.225,
    currentRatio: 1.635,
    totalRevenue: 28175998976,
    debtToEquity: 86.646,
    revenuePerShare: 30.668,
    returnOnAssets: 0.02744,
    returnOnEquity: 0.05588,
    grossProfits: 4069000000,
    freeCashflow: 2361125120,
    operatingCashflow: 4349000192,
    earningsGrowth: 0.694,
    revenueGrowth: 0.392,
    grossMargins: 0.21135001,
    ebitdaMargins: 0.14264,
    operatingMargins: 0.06115,
    profitMargins: 0.01973,
    financialCurrency: 'USD'
  }
}
```

<a name="fundOwnership"></a>
### fundOwnership

```js
await yahooFinance.quoteSummary('', { modules: [ "fundOwnership" ] });


```

<a name="fundPerformance"></a>
### fundPerformance

```js
await yahooFinance.quoteSummary('', { modules: [ "fundPerformance" ] });


```

<a name="fundProfile"></a>
### fundProfile

```js
await yahooFinance.quoteSummary('', { modules: [ "fundProfile" ] });


```

<a name="incomeStatementHistory"></a>
### incomeStatementHistory

```js
await yahooFinance.quoteSummary('', { modules: [ "incomeStatementHistory" ] });


```

<a name="incomeStatementHistoryQuarterly"></a>
### incomeStatementHistoryQuarterly

```js
await yahooFinance.quoteSummary('', { modules: [ "incomeStatementHistoryQuarterly" ] });


```

<a name="indexTrend"></a>
### indexTrend

```js
await yahooFinance.quoteSummary('', { modules: [ "indexTrend" ] });


```

<a name="industryTrend"></a>
### industryTrend

```js
await yahooFinance.quoteSummary('', { modules: [ "industryTrend" ] });


```

<a name="insiderHolders"></a>
### insiderHolders

```js
await yahooFinance.quoteSummary('', { modules: [ "insiderHolders" ] });


```

<a name="insiderTransactions"></a>
### insiderTransactions

```js
await yahooFinance.quoteSummary('', { modules: [ "insiderTransactions" ] });


```

<a name="institutionOwnership"></a>
### institutionOwnership

```js
await yahooFinance.quoteSummary('', { modules: [ "institutionOwnership" ] });


```

<a name="majorDirectHolders"></a>
### majorDirectHolders

```js
await yahooFinance.quoteSummary('', { modules: [ "majorDirectHolders" ] });


```

<a name="majorHoldersBreakdown"></a>
### majorHoldersBreakdown

```js
await yahooFinance.quoteSummary('', { modules: [ "majorHoldersBreakdown" ] });


```

<a name="netSharePurchaseActivity"></a>
### netSharePurchaseActivity

```js
await yahooFinance.quoteSummary('', { modules: [ "netSharePurchaseActivity" ] });


```

<a name="price"></a>
### price

```js
await yahooFinance.quoteSummary('', { modules: [ "price" ] });

{
  price: {
    maxAge: 1,
    preMarketSource: 'FREE_REALTIME',
    postMarketChangePercent: 0.006599537,
    postMarketChange: 5.76001,
    postMarketTime: new Date("2021-02-03T00:59:57.000Z"),
    postMarketPrice: 878.55,
    postMarketSource: 'DELAYED',
    regularMarketChangePercent: 0.039270766,
    regularMarketChange: 32.97998,
    regularMarketTime: new Date("2021-02-02T21:00:01.000Z"),
    priceHint: 2,
    regularMarketPrice: 872.79,
    regularMarketDayHigh: 880.5,
    regularMarketDayLow: 842.2006,
    regularMarketVolume: 24346213,
    regularMarketPreviousClose: 839.81,
    regularMarketSource: 'FREE_REALTIME',
    regularMarketOpen: 844.68,
    exchange: 'NMS',
    exchangeName: 'NasdaqGS',
    exchangeDataDelayedBy: 0,
    marketState: 'PREPRE',
    quoteType: 'EQUITY',
    symbol: 'TSLA',
    underlyingSymbol: null,
    shortName: 'Tesla, Inc.',
    longName: 'Tesla, Inc.',
    currency: 'USD',
    quoteSourceName: 'Delayed Quote',
    currencySymbol: '$',
    fromCurrency: null,
    toCurrency: null,
    lastMarket: null,
    marketCap: 827318468608
  }
}

```

<a name="quoteType"></a>
### quoteType

```js
await yahooFinance.quoteSummary('', { modules: [ "quoteType" ] });


```

<a name="recommendationTrend"></a>
### recommendationTrend

```js
await yahooFinance.quoteSummary('', { modules: [ "recommendationTrend" ] });


```

<a name="secFilings"></a>
### secFilings

```js
await yahooFinance.quoteSummary('', { modules: [ "secFilings" ] });


```

<a name="sectorTrend"></a>
### sectorTrend

```js
await yahooFinance.quoteSummary('', { modules: [ "sectorTrend" ] });


```

<a name="summaryDetail"></a>
### summaryDetail

```js
await yahooFinance.quoteSummary('AMZN', { modules: [ "summaryDetail" ] });

{
  summaryDetail: {
    maxAge: 1,
    priceHint: 2,
    previousClose: 3342.88,
    open: 3380,
    dayLow: 3361.125,
    dayHigh: 3427.74,
    regularMarketPreviousClose: 3342.88,
    regularMarketOpen: 3380,
    regularMarketDayLow: 3361.125,
    regularMarketDayHigh: 3427.74,
    payoutRatio: 0,
    beta: 1.198004,
    trailingPE: 98.82463,
    forwardPE: 52.008003,
    volume: 5245852,
    regularMarketVolume: 5245852,
    averageVolume: 3936666,
    averageVolume10days: 3828033,
    averageDailyVolume10Day: 3828033,
    bid: 0,
    ask: 0,
    bidSize: 800,
    askSize: 900,
    marketCap: 1695918456832,
    fiftyTwoWeekLow: 1626.03,
    fiftyTwoWeekHigh: 3552.25,
    priceToSalesTrailing12Months: 4.8740993,
    fiftyDayAverage: 3214.06,
    twoHundredDayAverage: 3187.6775,
    currency: 'USD',
    fromCurrency: null,
    toCurrency: null,
    lastMarket: null,
    algorithm: null,
    tradeable: false
  }
}
```

<a name="summaryProfile"></a>
### summaryProfile

```js
await yahooFinance.quoteSummary('', { modules: [ "summaryProfile" ] });

{
  summaryProfile: {
    address1: '410 Terry Avenue North',
    city: 'Seattle',
    state: 'WA',
    zip: '98109-5210',
    country: 'United States',
    phone: '206-266-1000',
    website: 'http://www.amazon.com',
    industry: 'Internet Retail',
    sector: 'Consumer Cyclical',
    longBusinessSummary: 'Amazon.com, Inc. engages in the retail sale of consumer products and subscriptions in North America and internationally. The company operates through three segments: North America, International, and Amazon Web Services (AWS). It sells merchandise and content purchased for resale from third-party sellers through physical and online stores. The company also manufactures and sells electronic devices, including Kindle, Fire tablets, Fire TVs, Rings, and Echo and other devices; provides Kindle Direct Publishing, an online service that allows independent authors and publishers to make their books available in the Kindle Store; and develops and produces media content. In addition, it offers programs that enable sellers to sell their products on its Websites, as well as its stores; and programs that allow authors, musicians, filmmakers, skill and app developers, and others to publish and sell content. Further, the company provides compute, storage, database, and other AWS services, as well as fulfillment, advertising, publishing, and digital content subscriptions. Additionally, it offers Amazon Prime, a membership program, which provides free shipping of various items; access to streaming of movies and TV episodes; and other services. The company also operates in the food delivery business in Bengaluru, India. It serves consumers, sellers, developers, enterprises, and content creators. The company also has utility-scale solar projects in China, Australia, and the United States. Amazon.com, Inc. has a strategic relationship with NXP Semiconductors N.V. to deliver a cloud compute solution for vehicles that enable cloud-powered services. The company was founded in 1994 and is headquartered in Seattle, Washington.',
    fullTimeEmployees: 1125300,
    companyOfficers: [],
    maxAge: 86400
  }
}
```

<a name="topHoldings"></a>
### topHoldings

```js
await yahooFinance.quoteSummary('XLK', { modules: [ "topHoldings" ] });

{
  topHoldings: {
    maxAge: 1,
    stockPosition: 0.9984,
    bondPosition: 0,
    holdings: [
      {
        symbol: 'AAPL',
        holdingName: 'Apple Inc',
        holdingPercent: 0.22709998
      },
      {
        symbol: 'MSFT',
        holdingName: 'Microsoft Corp',
        holdingPercent: 0.19600001
      },
      /* ... */
    ],
    equityHoldings: {
      priceToEarnings: 35.1,
      priceToBook: 10.05,
      priceToSales: 6.4,
      priceToCashflow: 21.98
    },
    bondHoldings: {},
    bondRatings: [
      { bb: 0 },
      { aa: 0 },
      { aaa: 0 },
      { a: 0 },
      { other: 0 },
      { b: 0 },
      { bbb: 0 },
      { below_b: 0 },
      { us_government: 0 }
    ],
    sectorWeightings: [
      { realestate: 0 },
      { consumer_cyclical: 0 },
      { basic_materials: 0 },
      { consumer_defensive: 0 },
      { technology: 0.8672 },
      { communication_services: 0 },
      { financial_services: 0.113000005 },
      { utilities: 0 },
      { industrials: 0.0198 },
      { energy: 0 },
      { healthcare: 0 }
    ]
  }
}
```

<a name="upgradeDowngradeHistory"></a>
### upgradeDowngradeHistory

```js
await yahooFinance.quoteSummary('GME', { modules: [ "upgradeDowngradeHistory" ] });

{
  upgradeDowngradeHistory: {
    history: [
      {
        epochGradeDate: new Date("2021-01-27T13:56:33.000Z"),
        firm: 'B of A Securities',
        toGrade: 'Underperform', // "Underperform", "Hold", etc (see schema)
        fromGrade: '',
        action: 'main' // "down", "up", "init"
      },
      /* ... */
    ],
    maxAge: 86400
  }
}
```
