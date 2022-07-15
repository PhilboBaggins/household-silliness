
ALL := plus.png equals.png assembly.png lots-of-resistors.png              resistor-sandbox.png
BACKGROUND_COLOUR := white

all: ${ALL}

plus.png:
	magick -background ${BACKGROUND_COLOUR} -fill blue -pointsize 144 label:"+" $@

equals.png:
	magick -background ${BACKGROUND_COLOUR} -fill blue -pointsize 144 label:"=" $@

lots-of-resistors.png: resistors.jpg
	magick \
		-gravity Center \
		\( -background ${BACKGROUND_COLOUR} -fill black -pointsize 200 label:"(25,000 x " \) \
		$^ \
		\( -background ${BACKGROUND_COLOUR} -fill black -pointsize 200 label:")" \) \
		+append $@

# Temporary placeholder
resistor-sandbox.png:
	magick -background ${BACKGROUND_COLOUR} -fill red -pointsize 200 label:"AWESOME" $@

assembly.png: AliExpress-sandbox.webp plus.png lots-of-resistors.png equals.png resistor-sandbox.png
	magick convert -gravity Center -append $^ $@

clean:
	rm -f ${ALL}
