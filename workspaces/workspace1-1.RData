install.packages("tm")


library(tm)
workDir <- "D:\\KSZ\\PJN\\TextMining12s"

setwd(workDir)

inputDir <- ".\\data"
outputDir <- ".\\results"
scriptsDir <- ".\\scripts"
workspaceDir <- ".\\workspaces"

dir.create(outputDir, showWarnings = FALSE)

corpusDir <- paste(inputDir,"\\", "Literatura", sep = "")
corpus <- VCorpus(DirSource(corpusDir,pattern = "*.txt", encoding = "UTF-8"), readerControl = list(language = "pl_PL"))

View(corpus)

//wstepne przetwarzanie

corpus <- tm_map(corpus, removeNumbers)
corpus <- tm_map(corpus, removePunctuation)
corpus <- tm_map(corpus, content_transformer(tolower))
stoplistFile <- paste(
  inputDir,
  "\\",
  "stopwords_pl.txt",
  sep = ""
)

stoplist <- readLines(
  stoplistFile,
  encoding = "UTF-8"
)
corpus <- tm_map(corpus, removeWords, stoplist)
corpus <- tm_map(corpus, stripWhitespace)
corpus <- tm_map(corpus, removeNumbers)