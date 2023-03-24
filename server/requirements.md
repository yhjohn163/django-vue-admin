# celery==5.1.2
# Django==3.2.6
# django-celery-beat==2.2.1
# django-cors-headers==3.7.0
# django-filter==2.4.0
# django-simple-history==3.0.0
# djangorestframework==3.12.4
# djangorestframework-simplejwt==4.7.2
# drf-yasg==1.20.0
# psutil==5.8.0

celery==5.2.7
Django==4.1.7
django-celery-beat==2.5.0
django-cors-headers==3.14.0
django-filter==22.1
django-simple-history==3.3.0
# djangorestframework==3.14.0
djangorestframework==3.12.0
djangorestframework-simplejwt==5.2.2
drf-yasg2==1.19.4
psutil==5.9.4
django-auth-ldap==4.1.0
# pyodbc==4.0.35
pyodbc --no-binary=pyodbc==4.0.35
mssql-django==1.2

## django-pyodbc-azure
# pyodbc==4.0.35
# django-pyodbc-azure==2.1.0.0
# Successfully installed Django-2.1.15 django-pyodbc-azure-2.1.0.0
# The conflict is caused by:
#     The user requested Django==3.2.6
#     django-celery-beat 2.2.1 depends on Django<4.0 and >=2.2
#     django-cors-headers 3.7.0 depends on Django>=2.2
#     django-filter 2.4.0 depends on Django>=2.2
#     djangorestframework 3.12.4 depends on django>=2.2
#     djangorestframework-simplejwt 4.7.2 depends on django
#     drf-yasg 1.20.0 depends on Django>=2.2.16
#     django-auth-ldap 4.1.0 depends on Django>=2.2
#     django-pyodbc-azure 2.1.0.0 depends on Django<2.2 and >=2.1.0

# To fix this you could try to:
# 1. loosen the range of package versions you've specified
# 2. remove package versions to allow pip attempt to solve the dependency conflict

## pyodbc==4.0.35
# django.core.exceptions.ImproperlyConfigured: Error loading pyodbc module: dlopen(/Users/yuhai/anaconda3/envs/djangovueadmin/lib/python3.8/site-packages/pyodbc.cpython-38-darwin.so, 0x0002): symbol not found in flat namespace '_SQLAllocHandle'

## https://github.com/mkleehammer/pyodbc/issues/1124
## https://stackoverflow.com/questions/66731036/unable-to-import-pyodbc-on-apple-silicon-symbol-not-found-sqlallochandle
# brew install unixodbc
# pip install --no-binary :all: pyodbc # for mac M1
# pip install --pre --no-binary :all: pyodbc

# ImportError: Could not import 'drf_yasg.generators.OpenAPISchemaGenerator' for API setting 'DEFAULT_GENERATOR_CLASS'. ImportError: Module "drf_yasg.generators" does not define a "OpenAPISchemaGenerator" attribute/class.

# https://github.com/axnsan12/drf-yasg/issues/813
# change djangorestframework==3.14.0 to djangorestframework==3.12.0


## django.db.utils.Error: ('01000', "[01000] [unixODBC][Driver Manager]Can't open lib 'ODBC Driver 17 for SQL Server' : file not found (0) (SQLDriverConnect)")

# https://pypi.org/project/mssql-django/
# https://www.mssqltips.com/sqlservertip/6693/python-django-tutorial-website-sql-server-database/


# https://github.com/microsoft/mssql-docker/issues/448
# import pyodbc
# print(pyodbc.drivers())
# >>> ['ODBC Driver\xa017\xa0for\xa0SQL Server']

# (base) ➜  ~ odbcinst -j
# unixODBC 2.3.9
# DRIVERS............: /etc/odbcinst.ini
# SYSTEM DATA SOURCES: /etc/odbc.ini
# FILE DATA SOURCES..: /etc/ODBCDataSources
# USER DATA SOURCES..: /Users/yuhai/.odbc.ini
# SQLULEN Size.......: 8
# SQLLEN Size........: 8
# SQLSETPOSIROW Size.: 8

# /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
# brew tap microsoft/mssql-release https://github.com/Microsoft/homebrew-mssql-release
# brew tap microsoft/mssql-release /Users/yuhai/bin/msserver/homebrew-mssql-release
# brew update
# HOMEBREW_ACCEPT_EULA=Y brew install msodbcsql17 mssql-tools

# >>> import pyodbc
# >>> print(pyodbc.drivers())
# ['ODBC Driver 17 for SQL Server']
# >>>
# https://github.com/mkleehammer/pyodbc/issues/717
# >>> print(pyodbc.dataSources())
# {}

# https://stackoverflow.com/questions/69772640/why-do-i-not-have-odbc-driver-17-in-my-pyodbc-drivers-how-can-i-fix-this-in-ana
# https://learn.microsoft.com/en-us/sql/connect/odbc/download-odbc-driver-for-sql-server?view=sql-server-ver16
# https://learn.microsoft.com/en-us/sql/connect/odbc/linux-mac/install-microsoft-odbc-driver-sql-server-macos?view=sql-server-ver16
# https://learn.microsoft.com/en-us/sql/connect/odbc/linux-mac/installing-the-microsoft-odbc-driver-for-sql-server?view=sql-server-ver16&tabs=alpine18-install%2Calpine17-install%2Cdebian8-install%2Credhat7-13-install%2Crhel7-offline#17

# https://learn.microsoft.com/en-us/samples/azure-samples/mssql-django-samples/mssql-django-samples/
# https://www.connectionstrings.com/microsoft-odbc-driver-17-for-sql-server/

## django.db.utils.ProgrammingError: ('42000', '[42000] [Microsoft][ODBC Driver 17 for SQL Server][SQL Server]Cannot open database "sqlserver" requested by the login. The login failed. (4060) (SQLDriverConnect)')
# name is not correct. create "lilai" in sqlserver and assign "lilai" to name. Then the connection settings can work.

## django.db.utils.ProgrammingError: ('42000', "[42000] [Microsoft][ODBC Driver 17 for SQL Server][SQL Server]The size (10000) given to the column 'suggestion' exceeds the maximum allowed for any data type (8000). (131) (SQLExecDirectW)")
# https://github.com/xerial/sqlite-jdbc/releases
# https://github.com/xerial/sqlite-jdbc
# https://realpython.com/django-migrations-a-primer/
# https://docs.djangoproject.com/en/4.1/ref/django-admin/
# https://docs.djangoproject.com/en/4.1/topics/migrations/
# /Users/yuhai/Downloads/cdlAiSh/githubibm/django/yh_django_vue_admin/server/apps/wf/migrations/0001_initial.py
# /Users/yuhai/Downloads/cdlAiSh/githubibm/django/yh_django_vue_admin/server/apps/wf/models.py
# some fields' max_length=10000, change it to 4000