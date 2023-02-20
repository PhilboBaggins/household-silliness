
ALL := assembly.png lots-of-resistors.png              resistor-sandbox.png
BACKGROUND_COLOUR := white
FONT_SIZE := 200

all: ${ALL}

lots-of-resistors.png: resistors.jpg
	magick \
		-gravity Center \
		\( -background ${BACKGROUND_COLOUR} -fill black -pointsize ${FONT_SIZE} label:"(25,000 x " \) \
		$^ \
		\( -background ${BACKGROUND_COLOUR} -fill black -pointsize ${FONT_SIZE} label:")" \) \
		+append $@

# Temporary placeholder
resistor-sandbox.png:
	magick -background ${BACKGROUND_COLOUR} -fill red -pointsize ${FONT_SIZE} label:"AWESOME" $@

assembly.png: AliExpress-sandbox.png lots-of-resistors.png resistor-sandbox.png
	magick -gravity Center \
		AliExpress-sandbox.png \
		\( -background ${BACKGROUND_COLOUR} -fill blue -pointsize ${FONT_SIZE} label:"+" \) \
		lots-of-resistors.png \
		\( -background ${BACKGROUND_COLOUR} -fill blue -pointsize ${FONT_SIZE} label:"=" \) \
		resistor-sandbox.png \
		-append $@

clean:
	rm -f ${ALL}
