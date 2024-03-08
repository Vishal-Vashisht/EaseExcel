# EaseExcel
EaseExcel is a Python package designed to facilitate the transfer of data from databases to Excel. It seamlessly integrates with SQLAlchemy, supporting connections to various database types.

# Installation
If you encounter any errors during installation, you may need to install the following packages before trying again:

```bash
pip install SQLAlchemy XlsxWriter
```

# Usage
```python
# Import statments
from sqlalchemy import create_engine
from sqlalchemy import text
import asyncio

from EaseExcel.src.Excel.ease_excel import EaseExcel

```

```python
# Example 1
async def main():
    """
    In this example providing sql alchmey engine and sql query as argument

    These are required argument
    
    """
    engine = create_engine('postgresql+psycopg2://username:password@host:port/database')
   
    query = "select * from posts"

    await EaseExcel(
        sqlalchemy_engine=engine,
        SQL_query=query).build()

asyncio.run(main())

```

```python
# Example 2
async def main():
    """
    In this example providing sql alchmey engine, sql query and filename as argument

    file_name: it is optional argument if filename is not provided file will we created with
    default name.
    
    """
    engine = create_engine('postgresql+psycopg2://username:password@host:port/database')
   
    query = "select * from posts"

    await EaseExcel(
        sqlalchemy_engine=engine,
        SQL_query=query,
        file_name='Posts').build()

asyncio.run(main())

```

```python
# Example 3
async def main():
    """
    In this example providing sql alchmey engine, sql query and filename as argument

    file_name: it is optional argument if filename is not provided file will we created with
    default name.

    file_path: it is also a optional argument if this is not provided file will be create in current directory.
    
    """
    engine = create_engine('postgresql+psycopg2://username:password@host:port/database')
   
    query = "select * from posts"

    await EaseExcel(
        sqlalchemy_engine=engine,
        SQL_query=query,
        file_name='Posts'.
        file_path='<path>').build()

asyncio.run(main())

```