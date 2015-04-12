SOURCE?=../bytemark/data
TARGET?=data

default:
	@false

sync:
	mkdir -p $(TARGET)
	cp $(SOURCE)/* $(TARGET)/
	sed -i '/^\./s/^/#/ ; /^@/s/::/:/g' ${TARGET}/*
