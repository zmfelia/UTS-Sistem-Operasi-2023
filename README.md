# UTS-Sistem-Operasi-2023
1.	Jika diketahui 6 antrian proses (A, B, C, D, E, F) Dengan waktu kedatangan secara bersamaan yaitu: 0. Lama eksekusi tiap-tiap antrian proses secara berurutan 1,3,7,5,5,3. Hitunglah Turn Arround Time (TA) dengan menggunakan teknik penjadwalan proses: 
a. First In First Out (F I F O) 
b. Shortest Job First (S J F) 
c. Round Robin jika diketahui Quantum = 2 
2.	Dalam Penjadwalan proses terdapat tiga macam tipe penjadwalan, sebutkan dan jelaskan disertai gambar! 
3.	Sumber daya apa yang digunakan saat thread dibuat? Bagaimana mereka berbeda dari yang digunakan ketika suatu proses dibuat? 
4.	Output apa yang akan ditampilkan pada LINE A? Jelaskan! 
#include <sys/types.h>
#include <stdio.h>
#include <unistd.h>

int value = 5;

int main()
{
    pid_t pid;

    pid = fork();
    if (pid == 0) { /* child process */
        value += 15;
        return 0;
    }
    else if (pid > 0) { /* parent process */
        wait(NULL);
        printf("PARENT: value = %d\n", value); /* LINE A */
        return 0;
    }
}

