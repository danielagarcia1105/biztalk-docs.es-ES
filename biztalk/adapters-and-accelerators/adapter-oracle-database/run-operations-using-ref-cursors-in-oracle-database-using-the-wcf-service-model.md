---
title: Ejecutar operaciones de uso de los cursores REF cursor en la base de datos de Oracle mediante el modelo de servicio de WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF service model, performing operations using REF CURSORS
- REF CURSORS, performing operations
ms.assetid: b4cb9ede-eae1-44d7-8ba5-7e1261ccfa3b
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb527a4451388475ce69a5321d0d05616fc8afde
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model"></a>Ejecutar operaciones de uso de los cursores REF cursor en la base de datos de Oracle mediante el modelo de servicio de WCF
Un REF CURSOR es un tipo de datos de Oracle PL/SQL que representa un puntero a un conjunto de resultados en la base de datos de Oracle. El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] admite parámetros REF CURSOR en procedimientos, funciones y paquetes. Parámetros REF CURSOR pueden ser fuertemente tipado o débilmente tipada dependiendo de cómo se declaran en el procedimiento o función. Para obtener una explicación detallada de cómo se representan los parámetros REF CURSOR mediante la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], consulte [esquemas de mensaje para los cursores REF cursor](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-ref-cursors.md). En la tabla siguiente se resume cómo se representan los parámetros REF CURSOR en el modelo de servicio WCF.  
  
|Dirección del parámetro|Inflexible REF CURSOR|Débilmente tipada REF CURSOR|  
|-------------------------|--------------------------------|------------------------------|  
|IN|`string [PARAM_NAME]`<br /><br /> Cadena que contiene un bloque de PL/SQL. El bloque de PL/SQL debe devolver un REF CURSOR abierto mediante la ejecución de una instrucción "Abrir para SELECT" o mediante la invocación de una función o procedimiento. Un signo de interrogación (?) indica la posición de REF CURSOR devuelto por el parámetro. ¿Por ejemplo, "BEGIN abierto? SELECCIONE * DE MY_TABLE; END", o" BEGIN MY_PROC (PARM1,?, PARM2); FINALIZAR; ".|Igual que fuertemente tipados|  
|OUT|`out [PROC_NS].[PARAM_NAME]RECORD[] [PARAM_NAME]`<br /><br /> Un conjunto de registros fuertemente tipada.|`out [GENERIC_NS].GenRecordRow[] [PARAM_NAME]`<br /><br /> Un débilmente tipada genérico conjunto de registros.|  
|EN ESPERA|EN la salida de REF CURSOR parámetros se dividen en (IN) y un parámetro OUT. El parámetro IN se anexa "_IN" en la firma del método para distinguirlo del parámetro OUT. El parámetro OUT se representa mediante un conjunto de registros fuertemente tipada.<br /><br /> `string [PARAM_NAME]_IN`<br /><br /> `out [PROC_NS].[PARAM_NAME]RECORD[] [PARAM_NAME]`|EN la salida de REF CURSOR parámetros se dividen en (IN) y un parámetro OUT. El parámetro IN se anexa "_IN" para distinguirlo del parámetro OUT. El parámetro OUT se representa mediante un conjunto de registros débilmente tipada.<br /><br /> `string [PARAM_NAME]_IN`<br /><br /> `out [GENERIC_NS].GenRecordRow[] [PARAM_NAME]`|  
  
 [PARAM_NAME] = el nombre del parámetro en la definición de función o un procedimiento en la base de datos de Oracle; Por ejemplo, MYREFCURSOR.  
  
 [PROC_NS] = el espacio de nombres único generado para que contenga los parámetros del paquete, procedimiento o función; Por ejemplo, "microsoft.lobservices.oracledb._2007._03.SCOTT. Package.ACCOUNT_PKG. GET_ACTIVITY".  
  
 [GENERIC_NS] = el espacio de nombres en el que se define el conjunto de registros genérico, "microsoft.lobservices.oracledb._2007._03".  
  
## <a name="about-the-examples-used-in-this-topic"></a>Acerca de los ejemplos usados en este tema  
 Los ejemplos de este tema usan el paquete de Oracle SCOTT/paquetes/ACCOUNT_PKG. El siguiente procedimiento se utiliza desde ACCOUNT_PKG:  
  
```  
PROCEDURE get_activity(inrecs IN SYS_REFCURSOR, status OUT NUMBER, inoutrecs IN OUT activity_ref_type, outrecs OUT SYS_REFCURSOR);  
```  
  
 Una secuencia de comandos para generar este paquete se suministra con los ejemplos del SDK. Para obtener más información acerca de los ejemplos SDK, vea [ejemplos del SDK](../../core/samples-in-the-sdk.md).  
  
## <a name="ref-cursor-parameters-in-the-wcf-service-model"></a>Parámetros REF CURSOR en el modelo de servicio WCF  
 Los ejemplos siguientes muestran las clases y el cliente WCF generado para el procedimiento /SCOTT/Package/ACCOUNT_PKG/GET_ACTIVITY. Este procedimiento se débilmente tipada IN y parámetros de salida de REF CURSOR y un parámetro de IN OUT REF CURSOR fuertemente tipada.  
  
 Aquí está la firma del método que se genera en el cliente WCF para invocar GET_ACTIVITY.  
  
```  
public System.Nullable<decimal> GET_ACTIVITY(string INRECS, string INOUTRECS_IN, out microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACTIVITY.INOUTRECSRECORD[] INOUTRECS, out microsoft.lobservices.oracledb._2007._03.GenRecordRow[] OUTRECS);  
```  
  
 En el **GET_ACTIVITY**  /método siguiente, el parámetro IN OUT INOUTRECS se divide en dos parámetros:  
  
-   INOUTRECS_IN es una cadena que representa un parámetro IN REF CURSOR.  
  
-   INOUTRECS es un conjunto de registros fuertemente tipado que representa un parámetro de salida de REF CURSOR.  
  
 El débilmente tipada parámetro OUT, OUTRECS, se representa como un conjunto de registros genérico. El débilmente tipada en parámetro, INRECS, se representa como una cadena.  
  
### <a name="strongly-typed-out-ref-cursor-parameters"></a>Fuertemente tipadas REF CURSOR parámetros OUT  
 Inflexible OUT (o en espera) parámetros REF CURSOR se generan en un único espacio de nombres basado en el esquema, el paquete y el nombre del procedimiento o función en el que se utilizan. El procedimiento /SCOTT/Package/ACCOUNT_PKG/GET_ACTIVITY, este espacio de nombres es `microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACTIVITY`. El nombre de clase se forma anexando el nombre del parámetro con "Registro a" y la clase se compone de las propiedades que representan los campos de Oracle. A continuación muestra una parte de la clase que representa los registros fuertemente tipado generados para el parámetro INOUTRECS REF CURSOR.  
  
```  
namespace microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACTIVITY {  
    using System.Runtime.Serialization;  
  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
    [System.Runtime.Serialization.DataContractAttribute()]  
    public partial class INOUTRECSRECORD : object, System.Runtime.Serialization.IExtensibleDataObject {  
  
        ...  
  
        private System.Nullable<decimal> TIDField;  
  
        ...  
  
        [System.Runtime.Serialization.DataMemberAttribute()]  
        public System.Nullable<decimal> TID {  
            get {  
                return this.TIDField;  
            }  
            set {  
                this.TIDField = value;  
            }  
        }  
  
        ...  
  
    }  
}  
```  
  
### <a name="weakly-typed-out-ref-cursor-parameters"></a>Débilmente tipada REF CURSOR parámetros OUT  
 Débilmente tipada OUT (o en espera) parámetros REF CURSOR se representan mediante la clase de registro genérico. El conjunto de registros genérico siempre se genera en el mismo espacio de nombres y con el mismo nombre de clase, independientemente de la función o procedimiento. El código siguiente muestra la clase de registro genérico, **microsoft.lobservices.oracledb._2007._03.GenRecordRow**, que representa los registros para el parámetro OUTRECS OUT SYS_REFCURSOR (débilmente tipada).  
  
```  
namespace microsoft.lobservices.oracledb._2007._03 {  
    using System.Runtime.Serialization;  
  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
    [System.Runtime.Serialization.DataContractAttribute()]  
    public partial class GenRecordRow : object, System.Runtime.Serialization.IExtensibleDataObject {  
  
        private System.Runtime.Serialization.ExtensionDataObject extensionDataField;  
  
        private microsoft.lobservices.oracledb._2007._03.GenRecordColumn[] GenRecordColumnField;  
  
        public System.Runtime.Serialization.ExtensionDataObject ExtensionData {  
            get {  
                return this.extensionDataField;  
            }  
            set {  
                this.extensionDataField = value;  
            }  
        }  
  
        [System.Runtime.Serialization.DataMemberAttribute()]  
        public microsoft.lobservices.oracledb._2007._03.GenRecordColumn[] GenRecordColumn {  
            get {  
                return this.GenRecordColumnField;  
            }  
            set {  
                this.GenRecordColumnField = value;  
            }  
        }  
    }  
  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
    [System.Runtime.Serialization.DataContractAttribute()]  
    public partial class GenRecordColumn : object, System.Runtime.Serialization.IExtensibleDataObject {  
  
        private System.Runtime.Serialization.ExtensionDataObject extensionDataField;  
  
        private string ColumnNameField;  
  
        private string ColumnValueField;  
  
        private string ColumnTypeField;  
  
        public System.Runtime.Serialization.ExtensionDataObject ExtensionData {  
            get {  
                return this.extensionDataField;  
            }  
            set {  
                this.extensionDataField = value;  
            }  
        }  
  
        [System.Runtime.Serialization.DataMemberAttribute(IsRequired=true, EmitDefaultValue=false)]  
        public string ColumnName {  
            get {  
                return this.ColumnNameField;  
            }  
            set {  
                this.ColumnNameField = value;  
            }  
        }  
  
        [System.Runtime.Serialization.DataMemberAttribute(IsRequired=true)]  
        public string ColumnValue {  
            get {  
                return this.ColumnValueField;  
            }  
            set {  
                this.ColumnValueField = value;  
            }  
        }  
  
        [System.Runtime.Serialization.DataMemberAttribute(IsRequired=true, EmitDefaultValue=false, Order=2)]  
        public string ColumnType {  
            get {  
                return this.ColumnTypeField;  
            }  
            set {  
                this.ColumnTypeField = value;  
            }  
        }  
    }  
}  
```  
  
## <a name="using-ref-cursor-parameters-with-a-wcf-client"></a>Usar parámetros REF CURSOR con un cliente de WCF  
 Para invocar un procedimiento o función con parámetros REF CURSOR mediante un cliente WCF, realice lo siguiente:  
  
1.  Pasar una cadena para cada uno en o bloquear el parámetro OUT en REF CURSOR que contiene el código de PL/SQL para abrir el REF CURSOR. Este bloque puede ejecutar una instrucción Abrir para SELECT o invocar una función o procedimiento que devuelve un REF CURSOR abierto en un parámetro OUT.  
  
2.  Cuando finaliza el procedimiento o función, trabajar con los datos en los conjuntos de registros devueltos para cualquier OUT o IN OUT REF CURSOR parámetros. El conjunto de registros será un conjunto de los parámetros REF CURSOR débilmente tipada de registros genérico o un conjunto para los parámetros REF CURSOR fuertemente tipada de registros fuertemente tipada.  
  
 Para obtener más información sobre cómo invocar los procedimientos y funciones mediante el modelo de servicio WCF, vea [invocar funciones y procedimientos de la base de datos de Oracle mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md).  
  
 En el ejemplo siguiente se llama al procedimiento GET_ACTIVITY. Muestra dos formas de especificar un parámetro IN REF CURSOR:  
  
-   Para el parámetro en REF CURSOR, se especifica una instrucción Abrir para SELECT para devolver la actividad para 100001 de cuenta.  
  
-   Para el parámetro OUT en REF CURSOR, se invoca el procedimiento /SCOTT/Package/ACCOUNT_PKG/GET_ALL_ACTIVITY. Este procedimiento abre un REF CURSOR que contiene toda la actividad en la tabla ACCOUNTACTIVITY y lo devuelve como un parámetro OUT.  
  
 El ejemplo también muestra cómo leer datos desde el conjunto devuelto para los parámetros REF CURSOR fuertemente tipado tanto débilmente tipada de registros.  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
// Add WCF, WCF LOB Adapter SDK, and Oracle Database adapter namepaces  
using System.ServiceModel;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.OracleDB;  
  
// Include this namespace for WCF LOB Adapter SDK and Oracle Database adapter exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
// namespaces for strongly-typed and weakly typed REF CURSOR records  
using GET_ACTIVITYns = microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACTIVITY;  
using GENERICns = microsoft.lobservices.oracledb._2007._03;  
  
// In this sample, INRECS is opened by using an OPEN FOR statement, and  
// INOUTRECS_IN is opened by calling the GET_ALL_ACTIVITY procedure on Oracle.  
  
namespace OracleRefCursorsSM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // Create the client  
            SCOTTPackageACCOUNT_PKGClient accountPkgClient =   
                new SCOTTPackageACCOUNT_PKGClient("OracleDBBinding_SCOTT.Package.ACCOUNT_PKG");  
            // Set credentials  
            accountPkgClient.ClientCredentials.UserName.UserName = "SCOTT";  
            accountPkgClient.ClientCredentials.UserName.Password = "TIGER";  
  
            try  
            {  
  
                GET_ACTIVITYns.INOUTRECSRECORD[] strongCursor;  
                GENERICns.GenRecordRow[] weakCursor;  
  
                Console.WriteLine("Opening client");  
                // Open the client  
                accountPkgClient.Open();  
  
                Console.WriteLine("Invoking ACCOUNT_PKG.GET_ACTIVITY");  
                // Get  ACCOUNTACTIVITY records  
                // The IN REF CURSOR is set to all activity for account 100001  
                // The input part of the IN OUT ref cursor calls GET_ALL_ACTIVITY  
                // The weakly-typed OUT REF CURSOR parameter returns a list of activity for account 100001  
                // The strongly-typed IN OUT REF CURSOR parameter returns a list of all activity  
                string inRecsString = "BEGIN OPEN ? FOR SELECT * FROM ACCOUNTACTIVITY WHERE ACCOUNT=100001; END;";  
                string inoutRecsString = "BEGIN ACCOUNT_PKG.GET_ALL_ACTIVITY(?); END;";  
  
                accountPkgClient.GET_ACTIVITY(  
                                inRecsString,  
                                inoutRecsString,  
                                out strongCursor,  
                                out weakCursor);  
  
                // Display strong ref cursor (all activity)  
                Console.WriteLine("\nList of all activity returned (strong ref cursor)");  
                Console.WriteLine("Tx Id\tAccount\tAmount\tDate\t\t\tDescription");  
                for (int i = 0; i < strongCursor.Length; i++)  
                {  
                    Console.WriteLine("{0}\t{1}\t{2:C}\t{3}\t{4}",strongCursor[i].TID,  
                        strongCursor[i].ACCOUNT,   
                        strongCursor[i].AMOUNT,   
                        strongCursor[1].TRANSDATE,  
                        strongCursor[i].DESCRIPTION);  
                }  
  
                // Display weak ref cursor (account 100001)  
                Console.WriteLine("\nList of activity for account 100001 returned (weak ref cursor)");  
                Console.WriteLine("Tx Id\tAmount\tDate\t\t\tDescription");  
                for (int i = 0; i < weakCursor.Length; i++)  
                {  
                    Console.WriteLine("{0}\t{1:C}\t{2}\t{3}", weakCursor[i].GenRecordColumn[0].ColumnValue,  
                        weakCursor[i].GenRecordColumn[2].ColumnValue,  
                        weakCursor[i].GenRecordColumn[4].ColumnValue,  
                        weakCursor[i].GenRecordColumn[3].ColumnValue);  
                }  
  
                Console.WriteLine("\nHit <RETURN> to finish");  
                Console.ReadLine();  
            }  
            catch (TargetSystemException tex)  
            {  
                Console.WriteLine("Exception occurred on the Oracle Database");  
                Console.WriteLine(tex.InnerException.Message);  
            }  
            catch (ConnectionException cex)  
            {  
                Console.WriteLine("Exception occurred connecting to the Oracle Database");  
                Console.WriteLine(cex.InnerException.Message);  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("Exception is: " + ex.Message);  
                if (ex.InnerException != null)  
                {  
                    Console.WriteLine("Inner Exception is: " + ex.InnerException.Message);  
                }  
                throw ex;  
            }  
            finally  
            {  
                // Close the client  
                accountPkgClient.Close();  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar aplicaciones de bases de datos de Oracle mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)