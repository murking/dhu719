#
# This is a Shiny web application. You can run the application by clicking
# the 'Run App' button above.
#
# Find out more about building applications with Shiny here:
#
#    http://shiny.rstudio.com/
#
library(shiny)
library(RODBC)

conn <- odbcConnect("sql server",uid = "sa",pwd = "123","Database = 甲亢")
fmaleNum <- sqlQuery(conn,"SELECT count(*) FROM [甲亢病人基本信息] WHERE Sex ='女'")
sex <- tabPanel(
  "性别",
  imageOutput("sexpl")
  
)
age <- tabPanel(
  "年龄",
  imageOutput("agepl")
)
agemale <- tabPanel(
  "男性患者年龄",
  imageOutput("agemalepl")
)
ageFmale <- tabPanel(
  "女性患者年龄",
  imageOutput("agefmalepl")
)
pregnant <- tabPanel(
  "妊娠",
  imageOutput("prepl")
)
pregnantage <- tabPanel(
  "妊娠患者年龄",
  imageOutput("preagepl")
)
mpan <- tabsetPanel(
  sex,
  age,
  ageFmale,
  agemale,
  pregnant
)
ui <- fluidPage(mpan)
shinyApp(
  ui,
  server = function(input, output) {
    output$sexpl <- renderImage({
      return(list(src="images/sex.png"))
    },deleteFile = FALSE)
    
    output$agepl <- renderImage({
      return(list(src="images/age.png"))
    },deleteFile = FALSE)
    
    output$agemalepl <- renderImage({
      return(list(src="images/agemale.png"))
    },deleteFile = FALSE)
    
    output$agefmalepl <- renderImage({
      return(list(src="images/agefmale.png"))
    },deleteFile = FALSE)
    output$prepl <- renderImage({
      return(list(src="images/preganat.png"))
    },deleteFile = FALSE)
    output$preagepl <- renderImage({
      return(list(src="images/preage.png"))
    },deleteFile = FALSE)
  }
)

