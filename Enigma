#include <stdio.h>
#include <stdlib.h>
#include <conio.h>
#include <string.h>

// ------ENİGMA ŞİFRELEME-----

int x, y, ANAHTAR1, ANAHTAR2;

char ROTOR1[] = {'A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 'I', 'J', 'K', 'L', 'M', 'N', 'O', 'P', 'Q', 'R', 'S', 'T', 'U', 'V', 'W', 'X', 'Y', 'Z'};
char ROTOR2[] = {'A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 'I', 'J', 'K', 'L', 'M', 'N', 'O', 'P', 'Q', 'R', 'S', 'T', 'U', 'V', 'W', 'X', 'Y', 'Z'};
char SFVERI[250], SF, SFR[250];

void ROTORK(int ANAHTAR, int ROTOR) {

    char ART;
    if (ROTOR == 1) {
        for (x = 0; x < ANAHTAR - 1; x++) {
            ART = ROTOR1[0];
            for (y = 0; y < 25; y++)
                ROTOR1[y] = ROTOR1[y + 1];
            ROTOR1[25] = ART;
        }
    } else if (ROTOR == 2) {
        for (x = 0; x < ANAHTAR - 1; x++) {
            ART = ROTOR2[0];
            for (y = 0; y < 25; y++)
                ROTOR2[y] = ROTOR2[y + 1];
            ROTOR2[25] = ART;
        }
    }
}

void SIFRELEME(char DEGER[]) {
    for (x = 0; x < strlen(DEGER); x++) {
        for (y = 0; y < 26; y++) {
            if (DEGER[x] == ROTOR1[y]) {
                SFR[x] = ROTOR2[y];
                break;
            }
        }
    }
    FILE *DOSYA;
    DOSYA = fopen("Kripto.txt", "w");
    fprintf(DOSYA, "%s", SFR);
    fclose(DOSYA);
    printf("\nSifrelenmis Metin: %s\n", SFR);

}

int main() {


    printf("1.ROTOR ANAHTARINI GIRINIZ: ");
    scanf("%d", &ANAHTAR1);
    printf("2.ROTOR ANAHTARINI GIRINIZ: ");
    scanf("%d", &ANAHTAR2);
    printf("SIFRENELECEK METINI GIRINIZ: ");

    x = 0;
    do {
        SF = getche();
        if(SF>='A'&&SF<'Z'){
		SFVERI[x] = SF;
        x++;
    }
	 else
	{
    	if(SF != 13)
    	printf("\nLUTFEN DIZIDE VERILEN HARFLERI KULLANINIZ!");
	}
}	while (SF != 13 && x < 250);
    SFVERI[x] = '\0';
    ROTORK(ANAHTAR1, 1);
    ROTORK(ANAHTAR2, 2);
    SIFRELEME(SFVERI);
	

    return 0;
}
