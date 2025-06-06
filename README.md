# 📊 Dynamic Market Sales Analysis in Computer Hardware using Power BI

[![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=power-bi&logoColor=black)](https://powerbi.microsoft.com/)
[![Excel](https://img.shields.io/badge/Microsoft_Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)](https://www.microsoft.com/en-us/microsoft-365/excel)
[![SQL](https://img.shields.io/badge/SQL-336791?style=for-the-badge&logo=postgresql&logoColor=white)](https://www.postgresql.org/)

> A comprehensive Power BI dashboard solution for analyzing computer hardware sales performance, market trends, and business insights to drive data-driven decision making.

## 🎯 Project Overview

This project delivers an interactive and dynamic sales analysis dashboard for the computer hardware industry using Microsoft Power BI. The solution transforms raw sales data into actionable business insights through advanced data modeling, DAX calculations, and compelling visualizations.

## ✨ Key Features

🔍 **Dynamic Filtering & Slicing**
- Interactive date range selection
- Product category and brand filtering
- Geographic region analysis
- Sales channel segmentation

📈 **Comprehensive Analytics**
- Revenue trend analysis and forecasting
- Product performance metrics
- Customer segmentation insights
- Market share analysis
- Seasonal pattern identification

🎨 **Advanced Visualizations**
- Executive summary dashboard
- Drill-down capabilities
- Mobile-responsive design
- Real-time data refresh
- Custom KPI indicators

## 🚀 Dashboard Highlights

### Executive Summary Dashboard
- **Total Revenue**: Real-time revenue tracking with YoY growth
- **Sales Performance**: Monthly/quarterly performance indicators
- **Top Products**: Best-selling hardware categories
- **Geographic Insights**: Regional sales distribution
- **Profit Margins**: Category-wise profitability analysis

### Detailed Analytics
- Customer acquisition and retention rates
- Inventory turnover analysis
- Sales team performance metrics
- Market trend predictions
- Competitive analysis insights

## 📊 Sample Insights

![Dashboard Preview](images/dashboard_preview.png)

*Key findings from the analysis:*
- 📈 Gaming hardware shows 35% higher profit margins
- 🌍 North American market represents 42% of total revenue  
- 📱 Mobile accessories segment growing at 28% YoY
- 🏢 B2B sales contribute 60% of total volume

## 🛠️ Technical Stack

| Technology | Purpose |
|------------|---------|
| **Power BI Desktop** | Data modeling and visualization |
| **Power Query** | Data transformation and cleansing |
| **DAX (Data Analysis Expressions)** | Advanced calculations and measures |
| **Excel/CSV** | Data source integration |
| **SQL Server** | Database connectivity (optional) |

## 📁 Repository Structure

```
📦 Dynamic-Market-Sales-Analysis-in-Computer-Hardware-using-Power-BI/
├── 📊 dashboards/
│   ├── sales_analysis_dashboard.pbix
│   └── executive_summary.pbix
├── 📈 data/
│   ├── raw_data/
│   │   ├── sales_data.xlsx
│   │   ├── product_catalog.csv
│   │   └── customer_data.csv
│   └── processed_data/
│       └── cleaned_sales_data.xlsx
├── 📝 documentation/
│   ├── data_dictionary.md
│   ├── dax_formulas.md
│   └── user_guide.pdf
├── 🖼️ images/
│   ├── dashboard_preview.png
│   ├── kpi_overview.png
│   └── trend_analysis.png
├── 📋 scripts/
│   └── data_refresh_script.py
└── 📖 README.md
```

## 🚀 Quick Start Guide

### Prerequisites
- Microsoft Power BI Desktop (Latest version)
- Excel 2016 or newer
- Basic understanding of data analysis concepts

### Installation Steps

1. **Clone the Repository**
   ```bash
   git clone https://github.com/VaghaniUtsav/Dynamic-Market-Sales-Analysis-in-Computer-Hardware-using-Power-BI.git
   cd Dynamic-Market-Sales-Analysis-in-Computer-Hardware-using-Power-BI
   ```

2. **Open Power BI Dashboard**
   - Launch Power BI Desktop
   - Open `dashboards/sales_analysis_dashboard.pbix`
   - Refresh data connections if prompted

3. **Data Setup**
   - Ensure data files are in the correct `data/` directory
   - Update data source paths in Power BI if necessary
   - Refresh all data connections

4. **Explore the Dashboard**
   - Use interactive filters to explore different views
   - Drill down into specific metrics
   - Export insights as needed

## 📊 Key Performance Indicators (KPIs)

| Metric | Description | Target |
|--------|-------------|---------|
| **Total Revenue** | Monthly/Quarterly revenue tracking | > $2M/month |
| **Profit Margin** | Category-wise profitability | > 25% |
| **Customer Acquisition** | New customers per month | > 500/month |
| **Inventory Turnover** | Stock rotation efficiency | > 8x/year |
| **Market Share** | Share in hardware segments | > 15% |

## 🔧 Advanced Features

### Custom DAX Measures
```dax
// Revenue Growth Rate
Revenue Growth % = 
DIVIDE(
    [Total Revenue] - [Previous Period Revenue],
    [Previous Period Revenue],
    0
) * 100

// Customer Lifetime Value
Customer LTV = 
SUMX(
    VALUES(Customers[CustomerID]),
    [Average Order Value] * [Purchase Frequency] * [Customer Lifespan]
)
```

### Data Transformation Logic
- Automated data cleansing using Power Query
- Date dimension creation for time intelligence
- Product hierarchy modeling
- Customer segmentation algorithms

## 📱 Mobile Experience

The dashboard is optimized for mobile viewing with:
- Touch-friendly navigation
- Responsive layout design
- Key metrics summary view
- Offline capability

## 🔄 Data Refresh Schedule

- **Automated Refresh**: Every 4 hours during business days
- **Manual Refresh**: On-demand via Power BI Desktop
- **Data Sources**: Excel files, CSV imports, SQL connections
- **Refresh Duration**: ~5-10 minutes

## 🎓 Learning Outcomes

This project demonstrates proficiency in:
- **Power BI Development**: Advanced dashboard creation and design
- **Data Modeling**: Star schema implementation and relationships
- **DAX Programming**: Complex calculations and time intelligence
- **Business Intelligence**: KPI development and storytelling with data
- **Data Visualization**: Best practices for executive reporting

## 🤝 Contributing

Contributions are welcome! Please feel free to submit issues, feature requests, or pull requests.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📞 Contact & Support

**Utsav Vaghani**
- 📧 Email: [Utsav](https://mail.google.com/mail/u/0/?tab=rm&ogbl#inbox?compose=new)
- 💼 LinkedIn: [Utsav Vaghani](https://www.linkedin.com/in/utsav--vaghani/)
- 🐙 GitHub: [@VaghaniUtsav](https://github.com/VaghaniUtsav)

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Microsoft Power BI Community for inspiration and best practices
- Sample datasets from [Kaggle](https://www.kaggle.com/) and public sources
- Power BI documentation and learning resources

---

⭐ **If you found this project helpful, please consider giving it a star!** ⭐

*Built with ❤️ by Utsav Vaghani*
