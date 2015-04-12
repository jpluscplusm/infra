SOURCE?=../bytemark/data
TARGET?=data

default:
	@false

sync:
	mkdir -p $(TARGET)
	cp $(SOURCE)/* $(TARGET)/
	sed -i '/^[.^:]/s/^/#/ ; /^@/s/::/:/g ; /^@/s/:[0-9]*$$// ; s/^'\''/T/' $(TARGET)/*
	for F in $(TARGET)/*; do awk '/^T/{print $$1, "\"" $$2 "\"", $$3}/^[^T]/{print}' FS=':' OFS=':' $$F | sponge $$F; done

