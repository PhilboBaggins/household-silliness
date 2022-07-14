
ALL := plus.png equals.png assembly.png              resistors.png resistor-sandbox.png
BACKGROUND_COLOUR := white

all: ${ALL}

plus.png:
	magick -background ${BACKGROUND_COLOUR} -fill blue -pointsize 144 label:"+" $@

equals.png:
	magick -background ${BACKGROUND_COLOUR} -fill blue -pointsize 144 label:"=" $@

# TEmporary placeholders
resistors.png:
	magick -background ${BACKGROUND_COLOUR} -fill black -pointsize 200 label:"resistors" $@
resistor-sandbox.png:
	magick -background ${BACKGROUND_COLOUR} -fill red -pointsize 200 label:"AWESOME" $@

assembly.png: AliExpress-sandbox.webp plus.png resistors.png equals.png resistor-sandbox.png
	magick convert -gravity Center -append $^ $@

clean:
	rm -f ${ALL}
