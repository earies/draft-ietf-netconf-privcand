all: pyang yanglint

pyang:
	pyang --ietf --strict \
	    -p yang \
	    -f tree \
	    yang/ietf-netconf-private-candidate@2024-09-12.yang \
	    -o ietf-netconf-private-candidate.pyang-tree

yanglint:
	yanglint \
	    -p yang \
	    -f tree \
	    yang/ietf-netconf-private-candidate@2024-09-12.yang \
	    -o ietf-netconf-private-candidate.yanglint-tree

tests: test-json

test-json:
	@yanglint \
	   -p yang \
	   -f xml \
	   yang/ietf-netconf-private-candidate@2024-09-12.yang \
	   data/instance-data.xml
clean:
	rm *-tree

