---
title: Invocar funciones y procedimientos de la base de datos de Oracle mediante el modelo de servicio WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- how to, invoke functions and procedures using the WCF service model
- WCF service model, invoking functions and procedures
ms.assetid: 806fc803-3640-42d6-bdf9-53b08f9c7c50
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f1423d5945fe1c82ccc64027a28efa3c1777ca5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013157"
---
# <a name="invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model"></a>Invocar funciones y procedimientos de la base de datos de Oracle mediante el modelo de servicio de WCF
El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] superficies de procedimientos, funciones y paquetes como operaciones. En el modelo de servicio WCF estas operaciones se representan como métodos en un cliente de WCF. El modelo de servicio WCF y el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]:  
  
-   **Compatibilidad con las funciones**. El valor devuelto de la función de Oracle aparece como el valor devuelto del método de cliente WCF. Parámetros de Oracle se exponen como parámetros (con la dirección adecuada según se define a continuación) para el método de cliente WCF.  
  
-   **Admite procedimientos**. El primer parámetro del procedimiento Oracle OUT aparece como el valor devuelto del método de cliente WCF. Todos los demás parámetros de Oracle se exponen como parámetros (con la dirección adecuada según se define a continuación) para el método de cliente WCF.  
  
-   **Compatibilidad con paquetes Oracle**. El nombre de la operación y el espacio de nombres de sus tipos de parámetro se califican con el nombre del paquete.  
  
-   **Compatibilidad con sobrecarga funciones y procedimientos**.  
  
-   **Soporte técnico IN, OUT y en los parámetros para los tipos de datos básicos de Oracle para procedimientos y funciones de salida**. Los parámetros OUT se exponen como **out** los parámetros del método de cliente WCF y los parámetros OUT IN aparecen como **ref** parámetros.  
  
-   **EN soporte técnico, de salida y en parámetros REF CURSOR para los procedimientos y funciones, así como valores devueltos de función de salida**. Para obtener más información, consulte [realizar operaciones utilizando los cursores REF cursor en la base de datos de Oracle mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-database/run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model.md).  
  
-   **Compatibilidad con en, OUT y IN OUT registro escriba los parámetros de procedimientos y funciones, así como valores devueltos de función**. Para obtener más información, consulte [realizar operaciones utilizando tipos de registros en la base de datos de Oracle mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md).  
  
## <a name="about-the-examples-used-in-this-topic"></a>Acerca de los ejemplos usados en este tema.  
 Los ejemplos de este tema usan el /SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT sobrecargado procedimiento. Este procedimiento lee un registro de la tabla de SCOTT/cuenta basada en un identificador de cuenta o un nombre de cuenta. Una secuencia de comandos para generar este procedimiento y la tabla se suministra con los ejemplos del SDK. Para obtener más información acerca de los ejemplos SDK, consulte [ejemplos del SDK](../../core/samples-in-the-sdk.md).  
  
## <a name="the-wcf-client-class"></a>La clase de cliente WCF  
 En la tabla siguiente se muestra el nombre del cliente WCF y el método generado para los procedimientos, funciones y paquetes que el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] superficies. A menos que se sobrecarga una función o procedimiento, se utiliza un único cliente WCF para invocar todas las funciones en un esquema, todos los procedimientos en un esquema, o todas las funciones y procedimientos de un paquete.  
  
|Artefacto de Oracle|Nombre de operación de cliente WCF|Ejemplo|  
|---------------------|-------------------------------|-------------|  
|Procedimiento|[ESQUEMA] ProcedureClient. [PROC_NAME]|SCOTTProcedureClient.MYPROC|  
|Función|[ESQUEMA] FunctionClient. [FUNC_NAME]|SCOTTProcedureClient.MYFUNC|  
|Paquete (procedimiento o función)|[ESQUEMA] [Nombre_del_paquete] del paquete cliente. [PROC_NAME o FUNC_NAME]|SCOTTPackageMYPACKAGEClient.MYPROC|  
  
 [Esquema] = artefactos de la colección de Oracle; Por ejemplo, SCOTT.  
  
 [PROC_NAME] = el nombre de un procedimiento de Oracle; Por ejemplo, MYPROC.  
  
 [FUNC_NAME] = el nombre de una función de Oracle; Por ejemplo, MYFUNC.  
  
 [Nombre_del_paquete] = el nombre de un paquete de Oracle.  
  
 El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle registro representa parámetros de tipo y devolver valores, así como los conjuntos de resultados devueltos por parámetros REF CURSOR como tipos complejos de XML que contienen los datos de fila (o campos) de un registro de Oracle. En el modelo de servicio WCF, cada uno de estos tipos XML se representa como una clase. NET; las propiedades de la clase representan los campos del tipo de registro o conjunto de resultados de REF CURSOR. Tipos de registros de Oracle siempre se representan como clases .NET fuertemente tipadas. Sin embargo, un conjunto de resultados de REF CURSOR puede representarse como registros fuertemente tipada o débilmente tipada en función de si se declara el REF CURSOR propio fuertemente tipada como o débilmente tipada. Las clases que representan REF CURSOR o registro tipo parámetros (o valores devueltos) se generan en un único espacio de nombres según el procedimiento, función o paquete. En la tabla siguiente se muestra estos espacios de nombres.  
  
|Artefacto de Oracle|Espacio de nombres|Ejemplo|  
|---------------------|---------------|-------------|  
|Procedimiento|[BASE_NS]. [ESQUEMA]. Procedimiento. [PROC_NAME]|Microsoft.lobservices.OracleDB._2007._03.Scott. Procedure.MYPROC|  
|Función|[BASE_NS]. [ESQUEMA]. Función. [FUNC_NAME]|Microsoft.lobservices.OracleDB._2007._03.Scott. Function.MYFUNC|  
|Paquete (procedimiento)|[BASE_NS]. [ESQUEMA]. Paquete. [NOMBRE_DEL_PAQUETE]. [PROC_NAME]|Microsoft.lobservices.OracleDB._2007._03.Scott. Package.MYPACKAGE.MYPROC|  
|Paquete (función)|[BASE_NS]. [ESQUEMA]. Paquete. [NOMBRE_DEL_PAQUETE]. [FUNC_NAME]|Microsoft.lobservices.OracleDB._2007._03.Scott. Package.MYPACKAGE.MYFUNC|  
|Genéricos (débilmente tipada) del conjunto de registros|[BASE_NS]|Microsoft.lobservices.OracleDB._2007._03|  
  
 [BASE_NS] = el espacio de nombres de adaptador base; Microsoft.lobservices.OracleDB._2007._03.  
  
 [Esquema] = artefactos de la colección de Oracle; Por ejemplo, SCOTT.  
  
 [PROC_NAME] = el nombre de un procedimiento de Oracle; Por ejemplo: MYPROC.  
  
 [FUNC_NAME] = el nombre de una función de Oracle; Por ejemplo, MYFUNC.  
  
 [Nombre_del_paquete] = el nombre de un paquete de Oracle.  
  
 Para obtener información sobre cómo se usan estos espacios de nombres para los parámetros de registro, vea [realizar operaciones utilizando tipos de registros en la base de datos de Oracle mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md). Para obtener información sobre cómo se usan estos espacios de nombres para los parámetros REF CURSOR, vea [realizar operaciones utilizando los cursores REF cursor en la base de datos de Oracle mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-database/run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model.md).  
  
 En general, los parámetros de Oracle y los valores devueltos se asignan como se indica a continuación en el método de cliente WCF:  
  
- Parámetros IN de Oracle se asignan a parámetros de (entrada). NET.  
  
- Los parámetros OUT de Oracle se asignan a .NET **out** parámetros.  
  
- Oracle en los parámetros se asignan a .NET **ref** parámetros.  
  
- Función que se asignan los valores devueltos para el valor devuelto del método.  
  
  Sin embargo, existen dos excepciones importantes:  
  
- Los parámetros IN OUT REF CURSOR de Oracle se dividen en una cadena de entrada y salida (**out**) conjunto de registros. Esto es porque el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] representa los parámetros IN REF CUSROR como cadenas y los parámetros de salida de REF CURSOR como tipos complejos (conjuntos de registros), estos no se pueden combinar en un solo parámetro.  
  
- El parámetro en un procedimiento de Oracle, primero se asigna al valor devuelto del método de cliente WCF. Es el comportamiento WCF estándar.  
  
  El ejemplo siguiente muestra parte de un procedimiento simple de Oracle (cargado en el esquema SCOTT) y la firma del método de cliente WCF que se genera para invocarlo. El procedimiento de Oracle tiene tres parámetros, tres parámetros IN OUT y tres parámetros OUT Sin embargo, el método de cliente WCF no asigna un parámetro para el primer parámetro de salida. En su lugar se asigna al valor devuelto de método.  
  
```  
CREATE or REPLACE PROCEDURE Sample_Procedure   
    (  
     INNUMBER      IN         NUMBER,  
     INVARCHAR     IN         VARCHAR2,  
     INDATE        IN         DATE,  
     INOUTNUMBER   IN OUT     NUMBER,  
     INOUTVARCHAR  IN OUT     VARCHAR,  
     INOUTDATE     IN OUT     DATE,  
     OUTNUMBER     OUT        NUMBER,  
     OUTVARCHAR    OUT        VARCHAR2,  
     OUTDATE       OUT        DATE  
    ) AS   
    BEGIN  
  
        ...  
  
    END;  
    /  
  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class SCOTTProcedureClient : System.ServiceModel.ClientBase<SCOTTProcedure>, SCOTTProcedure {  
  
    public System.Nullable<decimal> SAMPLE_PROCEDURE  
       (  
        System.Nullable<decimal> INNUMBER,   
        string INVARCHAR,   
        System.Nullable\<System.DateTime\> INDATE,   
        ref System.Nullable<decimal> INOUTNUMBER,   
        ref string INOUTVARCHAR,   
        ref System.Nullable\<System.DateTime\> INOUTDATE,   
        out string OUTVARCHAR,   
        out System.Nullable\<System.DateTime\> OUTDATE  
        );  
}  
```  
  
### <a name="support-for-overloaded-procedures-functions-and-packages"></a>Compatibilidad con procedimientos sobrecargados, funciones y paquetes  
 El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] admite sobrecarga procedimientos, funciones y paquetes anexando una cadena única para el identificador de nodo y el espacio de nombres que pone de manifiesto para cada artefacto sobrecargado. Esta cadena es "overload1" para la primera sobrecarga, "overload2" para la sobrecarga siguiente y así sucesivamente.  
  
 En el modelo de servicio WCF cada función o un procedimiento sobrecargado se representa mediante un único cliente WCF. Esto es diferente en el caso de no sobrecargar en el que todos las funciones de un esquema, todos los procedimientos en un esquema, o todos los procedimientos y funciones en un paquete se invocan el mismo cliente de WCF. En la tabla siguiente se muestra al cliente de WCF nombre y el método generada para procedimientos sobrecargados, funciones y paquetes.  
  
|Artefacto de Oracle|Nombre de cliente WCF|Ejemplo|  
|---------------------|---------------------|-------------|  
|Paquete sobrecargado (procedimiento)|[ESQUEMA] Paquetes [nombre_del_paquete] [PROC_NAME]] [OVERLOAD_ID] cliente. [PROC_NAME]|SCOTTPackageMYPACKAGEMYPROCoverload1Client.MYPROC|  
|Paquete sobrecargado (función)|[ESQUEMA] Paquetes [nombre_del_paquete] [FUNC_NAME]] [OVERLOAD_ID] cliente. [FUNC_NAME]|SCOTTPackageMYPACKAGEMYFUNCoverload1Client.MYFUNC|  
  
 [Esquema] = artefactos de la colección de Oracle; Por ejemplo, SCOTT.  
  
 [PROC_NAME] = el nombre de un procedimiento de Oracle; Por ejemplo: MYPROC.  
  
 [FUNC_NAME] = el nombre de una función de Oracle; Por ejemplo, MYFUNC.  
  
 [Nombre_del_paquete] = el nombre de un paquete de Oracle.  
  
 [OVERLOAD_ID] = la cadena única que identifica el artefacto sobrecargado; "overload1", "overload2" y así sucesivamente.  
  
 En la tabla siguiente se muestra el espacio de nombres que se genera para procedimientos sobrecargados, funciones y paquetes.  
  
|Artefacto de Oracle|Espacio de nombres|Ejemplo|  
|---------------------|---------------|-------------|  
|Paquete (procedimiento)|[BASE_NS]. [ESQUEMA]. Paquete. [NOMBRE_DEL_PAQUETE]. [PROC_NAME] [OVERLOAD_ID]|Microsoft.lobservices.OracleDB._2007._03.Scott. Package.MYPACKAGE.MYPROC.overload1|  
|Paquete (función)|[BASE_NS]. [ESQUEMA]. Paquete. [NOMBRE_DEL_PAQUETE]. [FUNC_NAME]. [OVERLOAD_ID]|Microsoft.lobservices.OracleDB._2007._03.Scott. Package.MYPACKAGE.MYFUNC.overload1|  
|Genéricos (débilmente tipada) del conjunto de registros|[BASE_NS]|Microsoft.lobservices.OracleDB._2007._03|  
  
 [BASE_NS] = el espacio de nombres de adaptador base; Microsoft.lobservices.OracleDB._2007._03.  
  
 [Esquema] = artefactos de la colección de Oracle; Por ejemplo, SCOTT.  
  
 [PROC_NAME] = el nombre de un procedimiento de Oracle; Por ejemplo: MYPROC.  
  
 [FUNC_NAME] = el nombre de una función de Oracle; Por ejemplo, MYFUNC.  
  
 [Nombre_del_paquete] = el nombre de un paquete de Oracle.  
  
 [OVERLOAD_ID] = la cadena única que identifica el artefacto sobrecargado; "overload1", "overload2" y así sucesivamente. El valor numérico en la cadena es el identificador de la sobrecarga del artefacto mantenida por la base de datos de Oracle.  
  
 El ejemplo siguiente muestra los clientes WCF y las firmas de método generadas para el procedimiento GET_ACCOUNT sobrecargado en el paquete ACCOUNT_PKG. (Las declaraciones de Oracle se incluyen). En este ejemplo se muestra cómo se genera un único cliente WCF para cada sobrecarga y cómo el método generado para cada cliente devuelve un conjunto de registros en un espacio de nombres único.  
  
```  
/* Procedure that takes account ID and returns record for existing account in the ACCOUNT table */  
PROCEDURE get_account(aid IN account.acctid%TYPE, acct OUT account%ROWTYPE) ;  
  
/* Procedure that takes account name and returns record for existing account in the ACCOUNT table */  
PROCEDURE get_account(aname IN account.name%TYPE, acct OUT account%ROWTYPE) ;  
  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload1Client : System.ServiceModel.ClientBase<SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload1>, SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload1 {  
  
    public microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNT.overload1.ACCTRECORD GET_ACCOUNT(System.Nullable<decimal> AID);  
}  
  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload2Client : System.ServiceModel.ClientBase<SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload2>, SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload2 {  
  
    public microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNT.overload2.ACCTRECORD GET_ACCOUNT(string ANAME);  
}  
```  
  
## <a name="invoking-functions-and-procedures"></a>Invocar funciones y procedimientos  
 Para invocar una función o un procedimiento con un cliente WCF, realice los pasos siguientes.  
  
1. Generar una clase de cliente WCF para la función de destino, el procedimiento o el paquete. Esta clase debe contener métodos para las operaciones que va a invocar en el artefacto de destino.  
  
   > [!NOTE]
   >  En el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]sobrecargado funciones y procedimientos que aparecen en la **operaciones y categorías disponibles** cuadro como [nombre].1, [nombre].2, [nombre].3 y así sucesivamente, donde [NAME] es el nombre del artefacto sobrecargado y el valor numérico es el identificador de sobrecarga en la base de datos de Oracle.  
  
2. Cree una instancia de la clase de cliente WCF y llamar a sus métodos para invocar la función o procedimiento.  
  
   Para obtener más información acerca de cómo crear una clase de cliente WCF e invocar operaciones en el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], consulte [general del modelo de servicio WCF con el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-service-model-with-the-oracle-database-adapter.md).  
  
   El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] ejecuta cada operación dentro de una transacción en la base de datos de Oracle.  
  
> [!IMPORTANT]
>  Las clases que representan el REF CURSOR y parámetros de tipo de registro o valores devuelven de funciones o procedimientos (y paquetes) se declaran en un espacio de nombres único para cada función o procedimiento. Por ejemplo, esto significa que se declarará un tipo de paquete REF CURSOR que se utiliza como valor devuelto en dos funciones diferentes en un espacio de nombres único para cada método de cliente WCF. O bien debe declarar variables independientes para almacenar estos diferentes valores de retorno o conversión correctamente la variable cuando se invoca uno de los métodos de cliente WCF.  
  
 El ejemplo siguiente muestra una llamada al procedimiento /SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT sobrecargado para obtener registros de cuenta de la tabla /SCOTT/ACCOUNT. Primero se crea un nuevo registro llamando al procedimiento /SCOTT/Package/ACCOUNT_PKG/CREATE_ACCOUNT. A continuación, se lee el nuevo registro back dos veces al llamar a las distintas sobrecargas de GET_ACCOUNT. Este ejemplo utiliza tres clientes WCF, uno para el procedimiento CREATE_ACCOUNT y uno para las sobrecargas GET_ACCOUNT. Los alias se usan para distinguir entre los espacios de nombres utilizados para el valor devuelto de GET_ACCOUNT. Un ejemplo completo está disponible en los ejemplos del SDK. Para obtener más información acerca de los ejemplos SDK, consulte [ejemplos del SDK](../../core/samples-in-the-sdk.md).  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
// Add WCF, WCF Adapter LOB SDK, and Oracle Database adapter namepaces  
using System.ServiceModel;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.OracleDB;  
  
// Include this namespace for WCF Adapter LOB SDK and Oracle Database adapter exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
// Alias client namespaces to shorten declarations of "shared" types   
using CREATE_ACCOUNTns = microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT;  
using GET_ACCOUNT_BY_IDns = microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNT.overload1;  
using GET_ACCOUNT_BY_NAMEns = microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNT.overload2;  
  
// This sample demonstrates calling overloaded packaged procedures on Oracle  
// First a new account is created by calling CREATE_ACCOUNT which takes two record parameters  
// Then the information for the new account is returned by calling an overloaded procedure GET_ACCOUNT  
// The first overload returns the account information by account ID  
// The second overload returns the account information by account name  
// Notice that different clients (and namespaces) are created for overloaded procedures and functions  
namespace OracleOverloadsSM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            decimal acctId;  
            string newAccountName = "Paula Bento";  
  
            Console.WriteLine("Creating clients");  
            // Create Client for CREATE_ACCOUNT Function  
            SCOTTPackageACCOUNT_PKGClient createAccountClient =   
                new SCOTTPackageACCOUNT_PKGClient("OracleDBBinding_SCOTT.Package.ACCOUNT_PKG");  
            // NOTE: user name and password are case-sensitive  
            createAccountClient.ClientCredentials.UserName.UserName = "SCOTT";  
            createAccountClient.ClientCredentials.UserName.Password = "TIGER";  
  
            // Create Client for GET_ACCOUNT Overload 1 -- takes ACCOUNT ID parameter  
            SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload1Client getAccountByIdClient =   
                new SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload1Client("OracleDBBinding_SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNT.overload1");  
            // NOTE: user name and password are case-sensitive  
            getAccountByIdClient.ClientCredentials.UserName.UserName = "SCOTT";  
            getAccountByIdClient.ClientCredentials.UserName.Password = "TIGER";  
  
            // Create Client for GET_ACCOUNT Overload 2 -- takes ACCOUNT NAME parameter  
            // NOTE: this client can be created from configuration; detail provided here  
            // for demonstration  
            OracleDBBinding overload2Binding = new OracleDBBinding();  
            EndpointAddress overload2EndpointAddress = new EndpointAddress("oracleDB://ADAPTER");  
            SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload2Client getAccountByNameClient =   
                new SCOTTPackageACCOUNT_PKGGET_ACCOUNToverload2Client(overload2Binding, overload2EndpointAddress);  
            // NOTE: user name and password are case-sensitive  
            getAccountByNameClient.ClientCredentials.UserName.UserName = "SCOTT";  
            getAccountByNameClient.ClientCredentials.UserName.Password = "TIGER";  
  
            try  
            {  
                Console.WriteLine("Opening clients -- please wait");  
                // Open clients  
                createAccountClient.Open();  
                getAccountByIdClient.Open();  
                getAccountByNameClient.Open();  
  
                Console.WriteLine("Creating new account");  
                // Create an account record  
                // NOTE: ACCTRECORD is defined in all three namespaces so specify the definition  
                // that corresponds to the client.  
                CREATE_ACCOUNTns.ACCTRECORD acctRec = new CREATE_ACCOUNTns.ACCTRECORD();  
  
                // Set any value for ACCTID -- new account ID is returned by CREATE_ACCOUNT  
                acctRec.ACCTID = 0;  
                acctRec.NAME = newAccountName;  
                acctRec.BALANCE = 10537;  
  
                // Create address record  
                CREATE_ACCOUNTns.ACCOUNT_PKGADDRESS_REC_TYPERECORD addrRec = new CREATE_ACCOUNTns.ACCOUNT_PKGADDRESS_REC_TYPERECORD();  
                addrRec.STREET = "456 Valley Rd";  
                addrRec.CITY = "New York";  
                addrRec.STATE = "NY";  
  
                // Create account  
                acctId = (decimal)createAccountClient.CREATE_ACCOUNT(acctRec, addrRec);  
                Console.WriteLine("New Account Created: AccountId = {0}, Name = {1}, Balance = {2:C}",  
                   acctId, acctRec.NAME, acctRec.BALANCE);  
  
                /* Get new account by Id */  
                GET_ACCOUNT_BY_IDns.ACCTRECORD acctById = getAccountByIdClient.GET_ACCOUNT(acctId);  
                Console.WriteLine("Account Returned by Id: AccountId={0}, Name={1}, Balance={2:C}",  
                    acctById.ACCTID, acctById.NAME, acctById.BALANCE);  
  
                /* Get new account by Name */  
                GET_ACCOUNT_BY_NAMEns.ACCTRECORD acctByName = getAccountByNameClient.GET_ACCOUNT(newAccountName);  
                Console.WriteLine("Account Returned by Name: AccountId={0}, Name={1}, Balance={2:C}",  
                    acctByName.ACCTID, acctByName.NAME, acctByName.BALANCE);  
  
                Console.WriteLine("Hit <RETURN> to finish");  
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
                // Close all the clients  
                createAccountClient.Close();  
                getAccountByIdClient.Close();  
                getAccountByNameClient.Close();  
            }  
  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)