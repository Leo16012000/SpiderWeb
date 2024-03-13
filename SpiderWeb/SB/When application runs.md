[[Component Scan]] -> crete object singleton -> put into IoC Container
If a Bean Y depend on Bean X, IoC will find in container:
if X exists -> get X out and inject to the bean Y (use @Autowired)
if X doesn't exist -> create 