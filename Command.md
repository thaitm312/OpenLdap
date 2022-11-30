# Add schema, module, etc.. in ldif format
sudo ldapadd -Q -Y EXTERNAL -H ldapi:/// -W -f test.ldif

# Modify schema, module, etc.. in ldif format using BindDN
sudo  ldapmodify -x -D cn=admin,dc=test,dc=com -W -f custom.ldif

# Get all active schema DN
sudo ldapsearch -b "cn=schema,cn=config" -H ldapi:/// -LLL -Q -Y EXTERNAL dn

# Get all active schema
sudo ldapsearch -b "cn=schema,cn=config" -H ldapi:/// -LLL -Q -Y EXTERNAL
