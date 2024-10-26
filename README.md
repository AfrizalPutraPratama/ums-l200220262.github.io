# ums-l200220262.github.io
Assignment IPSD


Langkah-Langkah :
Code Program:
from metaflow import FlowSpec, step

class AttendingClassesFlow(FlowSpec):

    @step
    def start(self):
        print("Memulai proses mengikuti kuliah informatika.")
        self.next(self.pay_tuition)

    @step
    def pay_tuition(self):
        print("Membayar biaya SPP...")
        # Simulasi proses pembayaran
        self.tuition_paid = True
        print("Biaya SPP telah dibayar.")
        self.next(self.attend_lectures)

    @step
    def attend_lectures(self):
        if not self.tuition_paid:
            print("Tidak dapat mengikuti kuliah tanpa membayar biaya SPP.")
            return
        print("Mengikuti kuliah...")
        self.next(self.submit_assignments)

    @step
    def submit_assignments(self):
        print("Mengumpulkan tugas...")
        # Simulasi pengumpulan tugas
        self.next(self.take_exams)

    @step
    def take_exams(self):
        print("Mengikuti ujian...")
        # Simulasi proses ujian
        self.next(self.receive_grades)

    @step
    def receive_grades(self):
        print("Menerima nilai...")
        # Simulasi perhitungan nilai
        self.final_grade = "A"
        print(f"Nilai akhir diterima: {self.final_grade}")
        self.next(self.end)

    @step
    def end(self):
        print("Proses selesai.")

if __name__ == '__main__':
    AttendingClassesFlow()


Langkah langkah menjalankan program:
1. menyiapkan env
conda create -n cs_classes python=3.8
conda activate cs_classes
pip install metaflow

2.Jalankan Metaflow
python attending_classes.py run

#output di terminal yang menunjukkan langkah-langkah yang diambil oleh mahasiswa.

visualisasi alur :
python attending_classes.py show

by : Afrizal Putra Pratama | L200220262

