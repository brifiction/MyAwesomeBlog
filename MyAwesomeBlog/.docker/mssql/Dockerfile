FROM microsoft/mssql-server-windows-developer

HEALTHCHECK --interval=30s --timeout=3s CMD [ "sqlcmd", "-Q", "select 1" ]

EXPOSE 1433