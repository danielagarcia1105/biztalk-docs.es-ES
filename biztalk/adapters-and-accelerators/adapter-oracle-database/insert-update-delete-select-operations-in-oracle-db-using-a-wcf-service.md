---
title: Insertar, actualizar, eliminar o seleccionar las operaciones de base de datos de Oracle mediante el modelo de servicio de WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, Delete operation
- WCF service model, Select operation
- WCF service model, Insert operation
- WCF service model, Update operation
ms.assetid: d1a9f44f-ea0b-4dd6-9489-fa0d963848c4
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f312f0fa967c08fabbc27c9269abaae68b9ac958
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217492"
---
# <a name="insert-update-delete-or-select-operations-in-oracle-database-using-the-wcf-service-model"></a>Insertar, actualizar, eliminar o seleccionar las operaciones de base de datos de Oracle mediante el modelo de servicio de WCF
La [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] expone un conjunto de básicas Insert, Update, Delete y las operaciones Select en las tablas de base de datos de Oracle y vistas. Mediante el uso de estas operaciones, puede realizar simple SELECT SQL INSERT, UPDATE y eliminar instrucciones calificadas por una cláusula WHERE en una tabla de destino o la vista. Para llevar a cabo operaciones más complejas, por ejemplo una consulta de SQL SELECT que utiliza el operador de combinación, puede usar la operación SQLEXECUTE. Para obtener más información sobre la operación SQLEXECUTE, consulte [realizar una operación de SQLEXECUTE en la base de datos de Oracle mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model.md).  
  
 En la tabla siguiente se resume las operaciones básicas de SQL que el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] superficies en tablas y vistas. Para obtener una descripción completa de estas operaciones, vea [esquemas de mensaje para insertar básico, Update, Delete y seleccione operaciones en tablas y vistas](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md).  
  
|Operación|Description|  
|---------------|-----------------|  
|Insert|La operación de inserción admite varias inserciones de registro o de forma masiva en la vista o tabla de destino:<br /><br /> -Una operación de inserción de registros varios inserta filas en una tabla o vista en función de un conjunto de registros proporcionado.<br />-Una operación de inserción masiva inserta filas en una tabla o vista basada en una lista especificada de consulta y de columnas SELECT de SQL. Los registros que devuelve la consulta se insertan en la tabla de destino basándose en la lista de columnas.|  
|Select|Realiza una consulta SELECT de SQL en la tabla de destino basándose en una lista de nombres de columna y una cadena de filtro que especifica una cláusula WHERE de SQL especificada.|  
|Update|Realiza una actualización en la tabla de destino. Los registros que se actualizarán se especifican mediante una cadena de filtro que especifica una cláusula WHERE de SQL. Los valores para la actualización se especifican en un registro de plantilla.|  
|DELETE|Realiza una eliminación en la tabla de destino basándose en una cláusula WHERE de SQL que se especifica en una cadena de filtro.|  
  
## <a name="about-the-examples-used-in-this-topic"></a>Acerca de los ejemplos usados en este tema  
 Los ejemplos en este tema usan la tabla /SCOTT/ACCOUNTACTIVITY. Una secuencia de comandos para generar esta tabla se suministra con los ejemplos del SDK. Para obtener más información acerca de los ejemplos SDK, vea [ejemplos del SDK](../../core/samples-in-the-sdk.md).  
  
## <a name="the-wcf-client-class"></a>La clase de cliente WCF  
 El nombre del cliente WCF que se genera para las operaciones básicas de SQL que el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] superficies se basa en el nombre de la tabla o vista, como se muestra en la tabla siguiente.  
  
|Artefacto de la base de datos de Oracle|Nombre de cliente WCF|  
|------------------------------|---------------------|  
|Tabla|[ESQUEMA] Cliente de la tabla [NombreTabla]|  
|Ver|[ESQUEMA] Cliente de la vista [VIEW_NAME]|  
  
 [Esquema] = artefactos de la colección de Oracle; Por ejemplo, SCOTT.  
  
 [NombreTabla] = el nombre de la tabla. Por ejemplo, ACCOUNTACTIVITY.  
  
 [VIEW_NAME] = el nombre de la vista.  
  
 La siguiente tabla muestra las firmas de método para las operaciones básicas de SQL en una tabla. Las firmas son los mismos para una vista, excepto en que el espacio de nombres de vista y el nombre sustituirán a las de la tabla.  
  
|Operación|Firma de método|  
|---------------|----------------------|  
|Insert|Insertar tiempo ([TABLE_NS]. [ RECORDINSERT NombreTabla] [] conjunto de registros, cadena COLUMN_NAMES, cadena de consulta);|  
|Select|[TABLE_NS]. [NOMBRETABLA] RECORDSELECT [] seleccione (string COLUMN_NAMES, cadena de filtro);|  
|Update|Actualizar larga ([TABLE_NS]. [ Table_name] RECORDUPDATE RECORDSET, cadena de filtro);|  
|DELETE|Eliminar larga (cadena de filtro);|  
  
 [TABLE_NS] = el nombre del espacio de nombres de tabla; Por ejemplo, microsoft.lobservices.oracledb._2007._03.SCOTT. Table.ACCOUNTACTIVITY.  
  
 [NombreTabla] = el nombre de la tabla. Por ejemplo, ACCOUNTACTIVITY.  
  
 Los tipos de registro utilizados por las operaciones de inserción, actualización y seleccionadas se definen en la tabla o ver el espacio de nombres.  
  
 El código siguiente muestra las firmas de método para una clase de cliente WCF habían generado para el Delete, Insert, Select y Update operaciones en la tabla ACCOUNTACTIVITY/SCOTT /.  
  
```  
public partial class SCOTTTableACCOUNTACTIVITYClient : System.ServiceModel.ClientBase<SCOTTTableACCOUNTACTIVITY>, SCOTTTableACCOUNTACTIVITY {  
  
    public long Delete(string FILTER);  
  
    public long Insert(microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDINSERT[] RECORDSET, string COLUMN_NAMES, string QUERY);  
  
    public microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDSELECT[] Select(string COLUMN_NAMES, string FILTER);  
  
    public long Update(microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDUPDATE RECORDSET, string FILTER);  
}  
```  
  
## <a name="invoking-the-basic-sql-operations"></a>Invocar las operaciones básicas de SQL  
 Para invocar las operaciones básicas de SQL en una tabla o vista con un cliente WCF, realice los pasos siguientes.  
  
1.  Generar una clase de cliente WCF para la tabla de destino o la vista. Esta clase debe contener métodos para las operaciones que va a invocar en el artefacto de destino.  
  
2.  Crear una instancia de la clase de cliente WCF e invocar sus métodos para realizar operaciones en la tabla o vista.  
  
 Para obtener más información acerca de cómo crear una clase de cliente WCF e invocar operaciones en el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], consulte [información general sobre el modelo de servicio de WCF con el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-service-model-with-the-oracle-database-adapter.md).  
  
 El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] se ejecuta cada operación dentro de una transacción en la base de datos de Oracle. Puede controlar el nivel de aislamiento de esta transacción estableciendo la **TransactionIsolationLevel** propiedad de enlace. Para obtener más información sobre la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] propiedades de enlace, consulte [trabajar con el adaptador de BizTalk para propiedades de enlace de base de datos de Oracle](https://msdn.microsoft.com/library/dd788467.aspx).  
  
 En las secciones siguientes proporcionan detalles sobre cómo invocar cada operación básica de SQL en el código.  
  
###  <a name="BKMK_InsertOperation"></a>Operación de inserción  
 En la tabla siguiente se muestra cómo establecer los parámetros de inserción de varios registros y las operaciones de inserción masiva.  
  
|Insertar tipo de operación|CONJUNTO DE REGISTROS|COLUMN_NAMES|QUERY|  
|---------------------------|---------------|-------------------|-----------|  
|Registro de varios|Una colección de INSERTRECORDS que se deben insertar en el destino.|null|null|  
|Masiva|null|Una lista delimitada por comas de nombres de columna en el destino; Por ejemplo, "TID, cuenta". La lista de columnas especifica las columnas en la que se deben colocar los resultados de la consulta en cada fila insertada. La consulta debe devolver un conjunto de resultados que coincida con las columnas especificadas en la lista de columnas en número y tipo.|Una consulta SELECT de SQL en una tabla de base de datos o vista que devuelve un conjunto de resultados para insertar en el destino; Por ejemplo, "SELECT (TID, cuenta) de cuenta de WHERE NEW_TRANSACTIONS = 100001". El conjunto de resultados debe coincidir con la lista de columnas en número y tipo.|  
  
 La operación de inserción, devuelve el número de registros que se insertan en el destino.  
  
> [!IMPORTANT]
>  En el modelo de servicio WCF, el conjunto de registros que se usan en la operación de inserción está fuertemente tipado. Puede establecer el valor de una columna nillable para **null** en un registro para excluir esa columna de la operación de inserción; sin embargo, no se puede establecer el valor de una columna no nillable para **null**. Esto significa que en una operación de inserción registra varios, debe suministrar valores para todas las columnas no nillable en cada registro. Además, no hay ninguna compatibilidad con streaming para las operaciones básicas de SQL cuando se usa el modelo de servicio WCF. Si la operación de insertar varios registra implica un conjunto de registros de gran tamaño, esto puede ser una consideración importante. Para obtener más información, consulte [limitaciones de invocar las operaciones básicas de SQL mediante el modelo de servicio de WCF](#BKMK_LimitationsInvoking).  
  
 El código siguiente muestra una varios registra operación de inserción (dos registros) destinado a la tabla ACCOUNTACTIVITY.  
  
```  
// Insert records  
                using (SCOTTTableACCOUNTACTIVITYClient aaTableClient =   
                    new SCOTTTableACCOUNTACTIVITYClient("OracleDBBinding_SCOTT.Table.ACCOUNTACTIVITY"))  
                {  
                    long recsInserted;  
  
                    aaTableClient.ClientCredentials.UserName.UserName = "SCOTT";  
                    aaTableClient.ClientCredentials.UserName.Password = "TIGER";  
  
                    try  
                    {  
                        aaTableClient.Open();  
                    }  
                    catch (Exception ex)  
                    {  
                        // handle exception  
                        Console.WriteLine("Exception: " + ex.Message);  
                        throw;  
                    }  
  
                    // Do a multiple record Insert of 2 records for account 100001  
  
                    microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDINSERT[] insertRecs =  
                        new microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDINSERT[2];  
  
                                  TID__COMPLEX_TYPE tid = new TID__COMPLEX_TYPE();  
                                  tid.InlineValue = "tidSequence.NextVal()";  
  
                                  ACCOUNT__COMPLEX_TYPE account = new ACCOUNT__COMPLEX_TYPE();  
                                  account.Value = 100001;  
  
                    AMOUNT__COMPLEX_TYPE amount = new AMOUNT__COMPLEX_TYPE();  
                    amount.Value = 400;  
  
                    TRANSDATE__COMPLEX_TYPE transdate = new TRANSDATE__COMPLEX_TYPE();  
                    transdate.Value = DateTime.Now.Date;  
  
                    PROCESSED__COMPLEX_TYPE processed = new PROCESSED__COMPLEX_TYPE();  
                    processed.Value = "n";  
  
                    DESCRIPTION__COMPLEX_TYPE description1 = new DESCRIPTION__COMPLEX_TYPE();  
                    description1.Value = "Inserted Record #1";  
  
                    DESCRIPTION__COMPLEX_TYPE description2 = new DESCRIPTION__COMPLEX_TYPE();  
                    description2.Value = "Inserted Record #2";  
  
                    insertRecs[0] =   
                        new microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDINSERT();  
                    insertRecs[0].TID = tid;  
                    insertRecs[0].ACCOUNT = account;  
                    insertRecs[0].AMOUNT = amount;  
                    insertRecs[0].TRANSDATE = transdate;  
                    insertRecs[0].DESCRIPTION = description1;  
                    insertRecs[0].PROCESSED = processed;  
  
                    insertRecs[1] =   
                        new microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDINSERT();  
                    insertRecs[1].TID = tid;  
                    insertRecs[1].ACCOUNT = account;  
                    insertRecs[1].AMOUNT = amount;  
                    insertRecs[1].TRANSDATE = transdate;  
                    insertRecs[1].DESCRIPTION = description2;  
                    insertRecs[1].PROCESSED = processed;  
  
                    try  
                    {  
                        recsInserted = aaTableClient.Insert(insertRecs, null, null);  
                    }  
                    catch (Exception ex)  
                    {  
                        // handle exception  
                        Console.WriteLine("Exception: " + ex.Message);  
                        throw;  
                    }  
  
                    Console.WriteLine("Insert Done: {0} records inserted", recsInserted);  
```  
  
### <a name="select-operation"></a>Seleccione la operación  
 En la tabla siguiente se muestra los parámetros para la operación de selección.  
  
|COLUMN_NAMES|FILTER|  
|-------------------|------------|  
|Una lista delimitada por comas de nombres de columna en el destino; Por ejemplo, "TID, cuenta". La lista de columnas especifica las columnas de destino que se deben devolver en el conjunto de resultados. Las columnas no especificadas en la lista de columnas se establecerá con sus valores predeterminados de .NET en el conjunto de registros devuelto. Para las columnas nillable, este valor es **null**.|El contenido de una cláusula WHERE de SQL que especifica las filas de destino de la consulta; Por ejemplo, "descripción = 'Insertar registro #1'". Puede establecer este parámetro en **null** para devolver todas las filas de destino.|  
  
 La operación Select devuelve un conjunto de registros fuertemente tipado basado en el tipo de fila del destino.  
  
> [!IMPORTANT]
>  No hay ninguna compatibilidad con streaming para las operaciones básicas de SQL cuando se usa el modelo de servicio WCF. Si la consulta devuelve un conjunto de registros grande, puede mejorar el rendimiento mediante el modelo de canal WCF. Para obtener más información, consulte [limitaciones de invocar las operaciones básicas de SQL mediante el modelo de servicio de WCF](#BKMK_LimitationsInvoking).  
  
 El código siguiente muestra una operación de selección que tenga como destino en la tabla ACCOUNTACTIVITY. Los registros devueltos se escriben en la consola.  
  
```  
// Declare a variable to hold the result set  
microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDSELECT[] selectRecords;  
  
// Select all records and write them to the console  
try  
{  
    selectRecords = aaTableClient.Select("*", null);  
}  
catch (Exception ex)  
{  
    // handle exception  
}  
  
Console.WriteLine("ACCOUNTACTIVITY before any operations");  
for (int i = 0; i \< selectRecords.Length; i++)  
{  
    Console.WriteLine("{0}\t{1}\t{2}\t{3}\t{4}", selectRecords[i].TID,  
    selectRecords[i].ACCOUNT,  
    selectRecords[i].AMOUNT,  
    selectRecords[i].TRANSDATE,  
    selectRecords[i].DESCRIPTION);  
}  
```  
  
> [!NOTE]
>  Este código omite los pasos para crear, configurar y abra la instancia de cliente WCF. Para obtener un ejemplo que incluye estos pasos, consulte [operación Insert](#BKMK_InsertOperation).  
  
### <a name="update-operation"></a>La operación de actualización  
 En la tabla siguiente se muestra los parámetros para la operación de actualización.  
  
|CONJUNTO DE REGISTROS|FILTER|  
|---------------|------------|  
|Un registro de plantilla fuertemente tipado basado en el tipo de fila del destino. El registro de plantilla especifica los valores de actualización para las filas de destino. Para las columnas de la fila nillable, puede especificar un valor null para indicar que no se debe actualizar la columna en las filas de destino.|El contenido de una cláusula WHERE de SQL que especifica las filas que se va a actualizarse en el destino. Por ejemplo, "descripción = 'Inserted registro #1'".|  
  
 La operación de actualización devuelve el número de filas eliminadas del destino.  
  
> [!IMPORTANT]
>  En el modelo de servicio WCF, el registro de plantilla que se utiliza en la operación de actualización está fuertemente tipado. Si una columna es "nillable", puede omitir la columna de la operación de actualización estableciendo su valor en **null** en el registro de plantilla; sin embargo, si una columna no tiene el atributo nillable, a continuación, debe establecer su valor en el registro de plantilla. Por ejemplo, si una columna es una clave principal, debe contener un valor. Para obtener más información, consulte [limitaciones de invocar las operaciones básicas de SQL mediante el modelo de servicio de WCF](#BKMK_LimitationsInvoking).  
  
 El código siguiente muestra una operación de actualización que tenga como destino en la tabla ACCOUNTACTIVITY.  
  
```  
long recsUpdated;  
  
...  
  
// Create updated template. The TID, TIME, AMOUNT, and DESCRIPTION fields will be updated  
microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDUPDATE updateRecord =  
    new microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDUPDATE();  
        updateRecord.TID = tidSequence.NextVal();  
        updateRecord.ACCOUNT = null;  
        updateRecord.AMOUNT = 300;  
        updateRecord.TRANSDATE = DateTime.Now.Date;  
        updateRecord.DESCRIPTION = "Updated Record #2";  
        updateRecord.PROCESSED = null;  
  
// Set filter string to specify the target record by using the DESCRIPTION field  
string filter = "DESCRIPTION = 'Inserted Record #2'";  
  
try  
{  
    recsUpdated = aaTableClient.Update(updateRecord, filter);  
}  
catch (Exception ex)  
{  
    // handle exception  
    ...  
}  
  
Console.WriteLine("{0} records updated", recsUpdated);  
```  
  
> [!NOTE]
>  Este código omite los pasos para crear, configurar y abra la instancia de cliente WCF. Para obtener un ejemplo que incluye estos pasos, consulte [operación Insert](#BKMK_InsertOperation).  
  
### <a name="delete-operation"></a>Operación de eliminación  
 En la tabla siguiente se muestra los parámetros para la operación de eliminación.  
  
|FILTER|  
|------------|  
|El contenido de una cláusula WHERE de SQL que especifica las filas que se eliminarán del destino. Por ejemplo, "descripción = 'Inserted registro #1'".|  
  
 La operación de eliminación, devuelve el número de filas eliminadas del destino. El código siguiente muestra una operación de eliminación que tenga como destino en la tabla ACCOUNTACTIVITY.  
  
```  
// Set filter string equal to the DESCRIPTION field of the target record  
string filter = "DESCRIPTION = 'Inserted Record #1'";  
  
try  
{  
    recsDeleted = aaTableClient.Delete(filter);  
}  
catch (Exception ex)  
{  
    // handle exception  
  
    ...  
}  
Console.WriteLine("{0} records deleted", recsDeleted);  
```  
  
> [!NOTE]
>  Este código omite los pasos para crear, configurar y abra la instancia de cliente WCF. Para obtener un ejemplo que incluye estos pasos, consulte la [operación Insert](#BKMK_InsertOperation).  
  
##  <a name="BKMK_LimitationsInvoking"></a>Limitaciones de invocar las operaciones básicas de SQL mediante el modelo de servicio WCF  
 Cuando se invocación las operaciones básicas de SQL mediante el uso de un cliente de WCF, existen las siguientes limitaciones:  
  
-   **Operación de inserción.** El conjunto de registros que se utiliza en una operación de inserción de registros varios está fuertemente tipadas y por lo tanto incluye todas las columnas de la fila. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] interpreta un valor null en un registro para indicar que la columna se debe excluir de la operación de inserción; sin embargo, no se puede excluir columnas no nillable porque no se puede establecer en un valor null. Por lo tanto, debe especificar valores para las columnas no nillable al realizar una operación de inserción varios registra.  
  
-   **Operación de inserción.** El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] interpreta un **DbNull** valor en una columna de datos nillable para indicar que se debe excluir la columna de una operación de inserción varios registra. Esto significa que no se puede establecer una columna nillable **DbNull** operación de inserción en la base de datos de Oracle en un registro de varios.  
  
-   **Operación de inserción.** No hay ninguna compatibilidad con streaming para varias operaciones de inserción de registros que implican un gran conjunto de registros.  
  
-   **La operación de actualización.** El registro de plantilla que se usa en una operación de actualización está fuertemente tipadas y por lo tanto incluye todas las columnas de la fila. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] interpreta un valor null en este registro para indicar que la columna se debe excluir de la operación de actualización; sin embargo, no se puede excluir columnas no nillable porque no se puede ellos con un valor null. Por lo tanto, debe especificar valores para las columnas no nillable al realizar una operación de actualización.  
  
-   **La operación de actualización.** El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] interpreta un **DbNull** valor en una columna de datos nillable en el registro de plantilla para indicar que la columna se debe excluir de la operación. Esto significa que no se puede establecer una columna nillable **DbNull** en la base de datos de Oracle mediante el uso de la operación de actualización.  
  
-   **Seleccione la operación.** No hay ninguna compatibilidad con streaming para consultas SELECT que devuelven un conjunto de registros grande.  
  
 Para escenarios donde estas limitaciones presentan desafíos, puede invocar la operación con el modelo del canal WCF porque:  
  
-   Mediante el modelo de canal WCF, puede excluir columnas de datos específicos de las operaciones Update e Insert.  
  
-   El modelo de canal WCF proporciona compatibilidad con streaming de nivel de nodo para las operaciones básicas de SQL que el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] expone.  
  
 Para obtener más información acerca de cómo utilizar el modelo de canal WCF con el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], consulte [desarrollar Oracle base de datos de aplicaciones utilizando el modelo del canal WCF](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md).  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar aplicaciones de base de datos de Oracle utilizando el modelo del canal de WCF](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)