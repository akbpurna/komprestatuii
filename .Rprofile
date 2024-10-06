# Pengecekan dan aktivasi renv jika ada
if (file.exists("renv/activate.R")) {
  source("renv/activate.R")
  
  # Auto-restore packages without prompting
  renv::restore(prompt = FALSE)
  
  # Optionally restart RStudio if necessary after sync
  # Uncomment the following line if you want to restart RStudio automatically after restore
  # .rs.restartR()
} else if (!requireNamespace("renv", quietly = TRUE)) {
  # Jika renv tidak tersedia, jalankan install.R untuk setup
  source("install.R")
}

# Membersihkan console otomatis saat RStudio dimulai
cat("\014")

# Atur lokasi kerja ke direktori sementara
# setwd(tempdir())

# Hapus file selama sesi, kecuali file-file penting
on.exit({
  files_to_keep <- c(
    ".Rprofile",      # file konfigurasi .Rprofile
    "DESCRIPTION",    # file DESCRIPSI
    "install.R",      # skrip install.R
    "jovyan.Rproj",   # file proyek RStudio
    "postBuild",      # file postBuild
    "python.ipynb",   # notebook Jupyter untuk Python
    "runtime.txt",    # file runtime.txt
    "scriptR.R",      # skrip R
    "renv",           # folder renv untuk manajemen paket
    ".Rbuildignore"   # file .Rbuildignore untuk mengecualikan file saat build paket
  )
  
  all_files <- list.files()              # Mendapatkan semua file di direktori proyek
  files_to_delete <- setdiff(all_files, files_to_keep)  # File yang tidak ada dalam files_to_keep akan dihapus
  unlink(files_to_delete, recursive = TRUE)  # Hapus file yang tidak ada di files_to_keep
})
