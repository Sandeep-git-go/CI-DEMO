appVersion = 10.0.32-fd9a755

.PHONY: build
build: 
	npm install --frozen-lockfile 
	npm cache clean --force
	npm run build

.PHONY: test
test: 
	npm install --frozen-lockfile
	npm cache clean --force
	npm run test
