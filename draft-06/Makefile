all: pyang yanglint

pyang:
	pyang --ietf --strict \
	    -p /data/a/yang/ietf \
	    -p yang \
	    -f tree \
	    yang/ietf-netconf-private-candidate@2024-09-12.yang \
	    -o ietf-netconf-private-candidate.pyang-tree

yanglint:
	yanglint \
	    -p /data/a/yang/ietf \
	    -p yang \
	    -f tree \
	    yang/ietf-netconf-private-candidate@2024-09-12.yang \
	    -o ietf-netconf-private-candidate.yanglint-tree

tests: test-json

test-json:
	@yanglint \
	   -p /data/a/yang/ietf \
	   -p yang \
	   -f xml \
	   yang/ietf-netconf-private-candidate@2024-09-12.yang \
	   data/instance-data.xml
clean:
	rm *-tree

