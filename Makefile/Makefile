NAME	:= getnextline.a    // Derlerken oluşturacağı dosya uzantısı herhangi birşey olabilir.
CC	:= gcc     // Derleme yapısı 
CFLAGS	:= -Wall -Wextra -Werror -I. -c    // Kontrol flagları
FILES	:= $(shell find . -type f ! -name "*.c"  -name "*.h") // find bul demek type(tipi file olan -name ismi *.c uzantısı ile olan dosyaları bul)
OBJ	:= $(FILES:%.c=%.o)   // .c uzantısı dosyaları .o ya çevir bu derleme işlemi yaparken bir hata oluşturmaması için .o uzantılı dosyalar oluşturur ki hata olduğunda .o yu .c ye çevirip eski halini tekrar kullanın.

BSRC	:= $(wildcard *.c)
B_OBJ	:= $(BSRC:%.c=%.o)

all: $(NAME)   // all komutu ilk olarak name e gider obc deki işlemi yapar ar arşivler OBJ ye gidip .c yi .o ya çevirir.

$(NAME): $(OBJ)
	ar -rcs $(NAME) $(OBJ)

bonus: $(OBJ) $(B_OBJ)
	ar -rcs $(NAME) $(OBJ) $(B_OBJ)   // projenizin bonus kısmı varsa ayrı bir şekilde derlemeye yarar.

clean:
	@rm -rf *.o   // clean .o uzantılı dosyaları siler merak etmeyin kendi dosyalarınıza birşey olmaz.

fclean: clean    // dosya ismiyle beraber .o uzantıları siler herhangi bir fazlalık kalmaz.
	@rm -f $(NAME)
re: fclean all   // önce .o uzantıları siler sonra all komutuna gidip tekrardan oluşturur yenileme işlemi diyebiliriz.

.PHONY: all bonus clean fclean re   // Buraya yazdığınız fonksiyonu bildiriyorsunuz mesala yukarda all bonus clean fclean gibi 
diyelimki proje klasörünüz olduğu konumda fclean diye bir dosya var ve bunu phony e bildirmediniz derleme çalışırken tahminimce hata olacaktır 
phony çakışma olmaması için eğer içerde fonksiyon isminde olan bir klasörünüz varsa ya ismini değiştirin yada bunu phony e bildirin.

***  MAKEFİLE NASIL DÜZELENMELİ ****

Öncelikle oluşturduğun projenin dizinine girersin Makefile isimli bir FİLE tipinde touch ile bir dosya oluşturursun FİLE ye çok kafa yorma..
Makefile isimli dosya oluşturduktan sonra içine bu komutları kopyalarsın tabi hangi uzantıları çalıştırmasını istiyorsan ona göre shell find kısmında
düzenleme yaparsın mesala başı ft_ ile başlayan *.c ile biten dosyaları ara diyebilirsin şu şekilde olur yukarı git ve FILES kısmında gözünde canlandır
$(shell find . -type f ! -name "ft_*.c")   bu kadar basit şimdi derleme yaparken sadece ft_ ile başlayan ve sonu .c uzantılı dosyaları derler
son olarak bütün ayarlamaları yukarıda yazılanlara göre yaptıktan sonra terminalde dosya konumunda iken make komutu ile derlemeyi başlatabilirsin..



**** YORUM SATIRLARINI SİLMEYİ UNUTMA *****
