# magma-s1ap-test

## Clone the repo
```
git clone https://github.com/magma/magma.git
```

## Spin up and provision the gateway VM
```	 
cd magma/lte/gateway
vagrant up magma && vagrant ssh magma
cd $MAGMA_ROOT/lte/gateway && make run
```

## Spin up and provision the s1ap tester's VM
```
cd magma/lte/gateway
vagrant up magma_test && vagrant ssh magma_test
cd $MAGMA_ROOT/lte/gateway/python && make
cd integ_tests && make
make integ_test TESTS=s1aptests/test_attach_detach.py
```
