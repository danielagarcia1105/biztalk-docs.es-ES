---
title: Ejecutar operaciones utilizando tipos de registros en la base de datos de Oracle mediante el modelo de servicio de WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- RECORD types, performing operations
- WCF service model, performing operations using RECORD types
ms.assetid: e7118a86-7470-48bb-aca0-6200dc0bb67c
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3de78290e29c4c1ddc1465e8a9463a6e9d7b86f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="run-operations-using-record-types-in-oracle-database-using-the-wcf-service-model"></a>Ejecutar operaciones utilizando tipos de registros en la base de datos de Oracle mediante el modelo de servicio de WCF
Tipos de registros de Oracle se usan para representar la información jerárquica de parámetros pasados a los procedimientos y funciones de PL/SQL. La [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] expone los tipos de registros como tipos XML complejos. En el modelo de servicio WCF, tipos de registros se deserializan en clases de .NET fuertemente tipadas. Los campos de registro se representan como propiedades en la clase.  
  
 El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] es compatible con los siguientes tipos de tipos de registros:  
  
-   Tipos de registro que se declaran como tabla % ROWTYPE parámetros en procedimientos almacenados y funciones.  
  
-   Tipos de registros que se declaran como parámetros de tipo de registro en los paquetes de PL/SQL, por ejemplo,`TYPE rec_type1 IS RECORD(name varchar2(100), age number(3));`  
  
-   Tipos de registros que contienen registros anidados.  
  
-   Tipos de registro que aparecen como IN, OUT o IN los parámetros OUT procedimientos o funciones.  
  
-   Tipos de registros que son los valores devueltos de funciones.  
  
 Este tema muestra cómo se representan los tipos de registros en el modelo de servicio WCF. Para obtener información acerca de cómo llamar a funciones y procedimientos de Oracle, vea [invocar funciones y procedimientos de la base de datos de Oracle mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md).  
  
## <a name="about-the-examples-used-in-this-topic"></a>Acerca de los ejemplos usados en este tema  
 Los ejemplos de este tema usan el paquete PL/SQL de Oracle de SCOTT/ACCOUNT_PKG. Los elementos siguientes se utilizan desde ACCOUNT_PKG.  
  
```  
TYPE address_rec_type IS RECORD (street customer.street%TYPE, city customer.city%TYPE, state customer.state%TYPE);  
  
FUNCTION create_account(acct IN ACCOUNT%ROWTYPE, addr IN address_rec_type) RETURN NUMBER;  
  
TYPE acctinfo_rec_type IS RECORD (acct account%ROWTYPE, address address_rec_type);  
  
FUNCTION get_accountinfo(aid NUMBER) RETURN acctinfo_rec_type;  
```  
  
 Una secuencia de comandos para generar este paquete se suministra con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] ejemplos. Para obtener más información, consulte la secuencia de comandos  
  
 Para obtener más información acerca de los ejemplos, vea [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).  
  
## <a name="record-types-in-the-wcf-service-model"></a>Tipos de registro en el modelo de servicio WCF  
 Tipos de registros de Oracle se representan como tipos XML complejos mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. En el modelo de servicio WCF, tipos complejos de XML se representan mediante una clase y las propiedades de esta clase representan los campos del tipo de registro de Oracle. La clase que representa un parámetro de tipo de registro se genera en un espacio de nombres que está calificada por el paquete (si existe) y el esquema de la función o procedimiento. Este espacio de nombres identifica de forma única la función o procedimiento del parámetro. Por ejemplo, se crean los parámetros de tipo de registro al procedimiento CREATE_ACCOUNT la ACCOUNT_PKG de paquete de Oracle en el espacio de nombres siguiente: `microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT`. Para obtener más información acerca de los espacios de nombres que se usa en el modelo de servicio WCF para representar tipos complejos en los procedimientos y funciones, vea [invocar funciones y procedimientos de la base de datos de Oracle mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md).  
  
 Mientras el espacio de nombres de un parámetro de tipo de registro está determinado por el procedimiento o función, el nombre de la clase generada por el parámetro de tipo de registro se determina a la forma en que se declara el tipo de registro. En la tabla siguiente muestra cómo se genera el nombre de la clase basada en los dos modos diferentes de declarar el parámetro de tipo de registro de Oracle.  
  
|Tipo de registro de Oracle|Nombre|Ejemplo|  
|------------------------|----------|-------------|  
|Parámetro de procedimiento o una función de la ROWTYPE del % tabla|[PARAMETER_NAME] REGISTRO|ACCTRECORD|  
|TIPO de parámetro de paquete de registro|[NOMBREDEPAQUETE] [RECORD_TYPE_NAME] REGISTRO|ACCOUNT_PKGACCTINFO_REC_TYPERECORD|  
  
 [PARAMETER_NAME] = el nombre del parámetro de procedimiento o una función; Por ejemplo, Acct.  
  
 [NombreDePaquete] = el nombre del paquete de Oracle.  
  
 [RECORD_TYPE_NAME] = el nombre especificado en la declaración de tipo de registro; Por ejemplo, ACCTINFO_REC_TYPE.  
  
 El código siguiente muestra las firmas de método del cliente WCF generado para dos funciones de Oracle. La función /SCOTT/Package/ACCOUNT_PKG/CREATE_ACCOUNT toma dos parámetros de IN de tipo de registro simples y la función /SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNTINFO devuelve un parámetro de tipo de registro que contiene dos tipos de registro anidados. Las declaraciones de función de Oracle se incluyen en la parte superior del código. Los parámetros de cada función se califican con un espacio de nombres único.  
  
```  
FUNCTION create_account(acct IN ACCOUNT%ROWTYPE, addr IN address_rec_type) RETURN NUMBER;  
FUNCTION get_accountinfo(aid NUMBER) RETURN acctinfo_rec_type;  
  
public partial class SCOTTPackageACCOUNT_PKGClient : System.ServiceModel.ClientBase<SCOTTPackageACCOUNT_PKG>, SCOTTPackageACCOUNT_PKG {  
  
    ...  
  
    public System.Nullable<decimal> CREATE_ACCOUNT(microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT.ACCTRECORD ACCT, microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT.ACCOUNT_PKGADDRESS_REC_TYPERECORD ADDR);  
  
    public microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNTINFO.ACCOUNT_PKGACCTINFO_REC_TYPERECORD GET_ACCOUNTINFO(System.Nullable<decimal> AID);  
}  
```  
  
 El código siguiente muestra las clases generadas para los parámetros de la función CREATE_ACCOUNT:`FUNCTION create_account(acct IN ACCOUNT%ROWTYPE, addr IN address_rec_type) RETURN NUMBER;`  
  
 Esta función tiene un parámetro declarado con una tabla % ROWTYPE y un parámetro declarado con un tipo de paquete de tipo de registro (`TYPE acctinfo_rec_type IS RECORD (acct account%ROWTYPE, address address_rec_type);`).  
  
```  
namespace microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT {  
  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
    [System.Runtime.Serialization.DataContractAttribute()]  
    public partial class ACCTRECORD : object, System.Runtime.Serialization.IExtensibleDataObject {…}  
  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
    [System.Runtime.Serialization.DataContractAttribute()]  
    public partial class ACCOUNT_PKGADDRESS_REC_TYPERECORD : object, System.Runtime.Serialization.IExtensibleDataObject {…}  
  
}  
```  
  
### <a name="representation-of-a-simple-record-type"></a>Representación de un tipo Simple  
 El código siguiente muestra cómo se representa un tipo de registro simple en el modelo de servicio WCF. Este código muestra la vista ampliada de la **ACCOUNTRECORD** clase que representa el parámetro de cuenta % ROWTYPE en la función CREATE_ACCOUNT. En esta clase, los campos de registro (columnas de fila) se representan como propiedades.  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
[System.Runtime.Serialization.DataContractAttribute()]  
public partial class ACCTRECORD : object, System.Runtime.Serialization.IExtensibleDataObject {  
  
    private System.Runtime.Serialization.ExtensionDataObject extensionDataField;  
  
    private System.Nullable<decimal> ACCTIDField;  
  
    private string NAMEField;  
  
    private System.Nullable<decimal> BALANCEField;  
  
    public System.Runtime.Serialization.ExtensionDataObject ExtensionData {  
        get {  
            return this.extensionDataField;  
        }  
        set {  
            this.extensionDataField = value;  
        }  
    }  
  
    [System.Runtime.Serialization.DataMemberAttribute()]  
    public System.Nullable<decimal> ACCTID {  
        get {  
            return this.ACCTIDField;  
        }  
        set {  
            this.ACCTIDField = value;  
        }  
    }  
  
    [System.Runtime.Serialization.DataMemberAttribute()]  
    public string NAME {  
        get {  
            return this.NAMEField;  
        }  
        set {  
            this.NAMEField = value;  
        }  
    }  
  
    [System.Runtime.Serialization.DataMemberAttribute(Order=2)]  
    public System.Nullable<decimal> BALANCE {  
        get {  
            return this.BALANCEField;  
        }  
        set {  
            this.BALANCEField = value;  
        }  
    }  
}  
```  
  
### <a name="representation-of-a-record-type-that-contains-nested-records"></a>Representación de un tipo de registro que contiene registros anidados  
 El código siguiente muestra la representación de un tipo de registro que contiene registros anidados. Este tipo de registro concreto es el valor devuelto de la función GET_ACCOUNTINFO (`FUNCTION get_accountinfo(aid NUMBER) RETURN acctinfo_rec_type;`). El ACCTINFO_REC_TYPE es un parámetro de paquete declarado mediante una construcción del tipo de registro (`TYPE acctinfo_rec_type IS RECORD (acct account%ROWTYPE, address address_rec_type);`). Contiene dos tipos de registro simple anidado, un registro de la fila de tabla % y un registro de tipo de registro del paquete. Estos dos registros simples se declaran en el mismo espacio de nombres como su registro primario y siguen la convención de nomenclatura esperada.  
  
```  
namespace microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNTINFO {  
    using System.Runtime.Serialization;  
  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
    [System.Runtime.Serialization.DataContractAttribute()]  
    public partial class ACCOUNT_PKGACCTINFO_REC_TYPERECORD : object, System.Runtime.Serialization.IExtensibleDataObject {  
  
        private System.Runtime.Serialization.ExtensionDataObject extensionDataField;  
  
        private microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNTINFO.ACCTRECORD ACCTField;  
  
        private microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNTINFO.ACCOUNT_PKGADDRESS_REC_TYPERECORD ADDRESSField;  
  
        public System.Runtime.Serialization.ExtensionDataObject ExtensionData {  
            get {  
                return this.extensionDataField;  
            }  
            set {  
                this.extensionDataField = value;  
            }  
        }  
  
        [System.Runtime.Serialization.DataMemberAttribute(IsRequired=true)]  
        public microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNTINFO.ACCTRECORD ACCT {  
            get {  
                return this.ACCTField;  
            }  
            set {  
                this.ACCTField = value;  
            }  
        }  
  
        [System.Runtime.Serialization.DataMemberAttribute(IsRequired=true)]  
        public microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNTINFO.ACCOUNT_PKGADDRESS_REC_TYPERECORD ADDRESS {  
            get {  
                return this.ADDRESSField;  
            }  
            set {  
                this.ADDRESSField = value;  
            }  
        }  
    }  
```  
  
## <a name="using-record-types-in-your-code"></a>Uso de tipos de registro en el código  
 Utilizar tipos de registros en el código es sencillo. Para invocar un procedimiento o función con un parámetro de tipo de registro, cree una instancia del tipo de registro o de tipos y pasarlo al método apropiado en el cliente WCF. Cuando el procedimiento o función, devuelve, se pueden leer las propiedades en cualquier tipo de espera o función devuelto o parámetros OUT en valores que se declaran como tipos de registros. Para obtener más información sobre cómo invocar los procedimientos y funciones mediante el modelo de servicio WCF, vea [invocar funciones y procedimientos de la base de datos de Oracle mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md).  
  
> [!IMPORTANT]
>  Parámetros de tipo de registro de Oracle (y valores devueltos de función) se califican con el espacio de nombres de su función o procedimiento (y paquete). Esto significa que un tipo de registro que se utiliza en dos procedimientos diferentes o funciones tendrá un espacio de nombres diferente para cada procedimiento o función. Debe ser seguro calificar el tipo de registro correctamente cuando se usa para una función o un procedimiento específico. Por ejemplo, un tipo de registro (declaración de tipo de registro) que se utiliza como un parámetro IN a dos funciones diferentes del paquete se declarará dos veces en el código de cliente WCF con cada declaración correspondiente al espacio de nombres único generado para cada función. Debe asegurarse de que utiliza el espacio de nombres correcto en el parámetro que se pasa a cada función respectiva.  
  
 En el ejemplo siguiente, se llama a la función CREATE_ACCOUNT con dos parámetros de registro simple. A continuación, se llama a la función GET_ACCOUNTINFO. Esta función devuelve un tipo de registro que contiene registros anidados. Seleccionó campo valores desde el registro devuelto se escriben en la consola. Pasos para establecer credenciales para la base de datos de Oracle y para abrir al cliente de WCF se omiten en este ejemplo.  
  
```  
// Add WCF, WCF Adapter LOB SDK, and Oracle Database adapter namepaces  
using System.ServiceModel;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.OracleDB;  
  
// Include this namespace for WCF Adapter LOB SDK and Oracle Database adapter exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
…  
  
// Create the client from configuration  
using (SCOTTPackageACCOUNT_PKGClient accountPkgClient = new SCOTTPackageACCOUNT_PKGClient("OracleDBBinding_SCOTT.Package.ACCOUNT_PKG"))  
{  
  
    ...  
  
    decimal acctId;  
  
    // Create an account record  
    // Note: ACCTRECORD is defined in both namespaces so specify the definition  
    // that corresponds to the client.  
  
    microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT.ACCTRECORD acctRec =   
        new microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT.ACCTRECORD();  
  
    // Set any value for ACCTID -- new account ID is returned by CREATE_ACCOUNT  
    acctRec.ACCTID = 0;  
    acctRec.NAME = "Anton Kirilov";  
    acctRec.BALANCE = 9583;  
  
    // Create address record  
    microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT.ACCOUNT_PKGADDRESS_REC_TYPERECORD addrRec = new microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT.ACCOUNT_PKGADDRESS_REC_TYPERECORD();  
    addrRec.STREET = "234 Main St";  
    addrRec.CITY = "Boston";  
    addrRec.STATE = "MA";  
  
    // Create account  
    try  
    {  
        acctId = (decimal)accountPkgClient.CREATE_ACCOUNT(acctRec, addrRec);  
    }  
    catch (Exception ex)  
    {  
        // handle exception  
        ...  
    }  
  
    ...  
  
    // Account info record  
    microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNTINFO.ACCOUNT_PKGACCTINFO_REC_TYPERECORD acctInfo =  
    new microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNTINFO.ACCOUNT_PKGACCTINFO_REC_TYPERECORD();  
  
    // Get account info for the account just created  
    // acctInfo is returned as a nested record type  
    try  
    {  
     acctInfo = accountPkgClient.GET_ACCOUNTINFO(acctId);  
    }  
    catch (Exception ex)  
    {  
    // handle exception  
    ...  
    }  
  
    // Write the account info to the console  
    Console.WriteLine("The account info is:");  
    Console.WriteLine("Name:\t\t\t{0}", acctInfo.ACCT.NAME);  
    Console.WriteLine("Street:\t\t\t{0}", acctInfo.ADDRESS.STREET);  
    Console.WriteLine("City:\t\t\t{0}", acctInfo.ADDRESS.CITY);  
    Console.WriteLine("State:\t\t\t{0}", acctInfo.ADDRESS.STATE);  
    Console.WriteLine("Account Id:\t\t{0}", acctInfo.ACCT.ACCTID);  
    Console.WriteLine("Account Balance:\t{0:C}", acctInfo.ACCT.BALANCE);  
  
    Console.WriteLine("\nHit <RETURN> to finish");  
    Console.ReadLine();  
    }  
}  
```  
  
## <a name="see-also"></a>Vea también  
 [Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)