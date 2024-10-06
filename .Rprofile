if (requireNamespace("renv", quietly = TRUE)) {
  renv::restore()
} else {
  source("install.R")
}

# Auto-activate and sync renv if present
if (file.exists("renv/activate.R")) {
  source("renv/activate.R")
  
  # Auto-restore packages without prompting
  renv::restore(prompt = FALSE)
  
  # Optionally restart RStudio if necessary after sync
  # Uncomment the following line if you want to restart RStudio automatically after restore
  .rs.restartR()
}
