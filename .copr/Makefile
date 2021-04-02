prepare:
	dnf install rpm-build git rpmdevtools "@Development Tools" -y
	rpmdev-setuptree

dist: prepare
	spectool -g -S -R $(spec)

srpm: dist
	rpmbuild -bs --define "_srcrpmdir $(outdir)" $(spec)

rpms: srpm
	rpmbuild -bb --define "_rpmdir $(outdir)" $(spec)

.PHONY: dist prepare rpms srpm
