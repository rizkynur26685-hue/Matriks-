# Matriks-
def main_game():
    # Inisialisasi skor awal untuk 4 kelompok
    skor = {
        "Kelompok 1": 0,
        "Kelompok 2": 0,
        "Kelompok 3": 0,
        "Kelompok 4": 0
    }
    
    print("==================================================")
    print("   GAME KUIS MATRIKS: PENJUMLAHAN & PENGURANGAN   ")
    print("==================================================\n")
    
    while True:
        print("\n--- MENU UTAMA ---")
        print("1. Lihat Skor Sementara")
        print("2. Tambah/Kurangi Poin Kelompok")
        print("3. Keluar dan Lihat Pemenang")
        
        pilihan = input("Pilih menu (1/2/3): ")
        
        if pilihan == "1":
            print("\n[ SKOR KELOMPOK SAAT INI ]")
            for kelompok, nilai in skor.items():
                print(f"- {kelompok}: {nilai} poin")
            print("-" * 30)
            
        elif pilihan == "2":
            print("\nPilih Kelompok:")
            print("1. Kelompok 1")
            print("2. Kelompok 2")
            print("3. Kelompok 3")
            print("4. Kelompok 4")
            
            k_pilih = input("Masukkan nomor kelompok (1-4): ")
            mapping_k = {"1": "Kelompok 1", "2": "Kelompok 2", "3": "Kelompok 3", "4": "Kelompok 4"}
            
            if k_pilih in mapping_k:
                nama_kelompok = mapping_k[k_pilih]
                try:
                    poin = int(input(f"Masukkan jumlah poin yang ditambah/dikurangi untuk {nama_kelompok} (Gunakan tanda minus '-' untuk mengurangi, misal: -10): "))
                    skor[nama_kelompok] += poin
                    print(f"Berhasil! Skor {nama_kelompok} sekarang: {skor[nama_kelompok]}")
                except ValueError:
                    print("Input poin harus berupa angka!")
            else:
                print("Pilihan kelompok tidak valid.")
                
        elif pilihan == "3":
            print("\n==================================================")
            print("               PERTANDINGAN BERAKHIR!             ")
            print("==================================================")
            print("\n[ SKOR AKHIR KELOMPOK ]")
            for kelompok, nilai in skor.items():
                print(f"- {kelompok}: {nilai} poin")
            
            # Mencari pemenang dengan skor tertinggi
            pemenang = max(skor, key=skor.get)
            print(f"\n🏆 SELAMAT KEPADA {pemenang.toUpperCase() if hasattr(pemenang, 'toUpperCase') else pemenang.upper()} SEBAGAI PEMENANG! 🏆")
            break
        else:
            print("Pilihan tidak valid, silakan coba lagi.")

if __name__ == "__main__":
    main_game()
