---
title: Ejecutar operaciones de uso de tipos de registro de base de datos de Oracle mediante el modelo de servicio WCF | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RECORD types, performing operations
- WCF service model, performing operations using RECORD types
ms.assetid: e7118a86-7470-48bb-aca0-6200dc0bb67c
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fd9bda9fc560310a882c5d48117cd823d544453
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004477"
---
# <a name="run-operations-using-record-types-in-oracle-database-using-the-wcf-service-model"></a><span data-ttu-id="8731a-102">Ejecutar operaciones de uso de tipos de registro de base de datos de Oracle mediante el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="8731a-102">Run Operations Using RECORD Types in Oracle Database using the WCF Service Model</span></span>
<span data-ttu-id="8731a-103">Tipos de registros de Oracle se usan para representar información jerárquica de los parámetros pasados a los procedimientos y funciones de PL/SQL.</span><span class="sxs-lookup"><span data-stu-id="8731a-103">Oracle RECORD types are used to represent hierarchical information in parameters passed to PL/SQL functions and procedures.</span></span> <span data-ttu-id="8731a-104">La [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] expone los tipos de registros como tipos XML complejos.</span><span class="sxs-lookup"><span data-stu-id="8731a-104">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces RECORD types as complex XML types.</span></span> <span data-ttu-id="8731a-105">En el modelo de servicio WCF, tipos de registros se deserializan en clases de .NET fuertemente tipadas.</span><span class="sxs-lookup"><span data-stu-id="8731a-105">In the WCF service model, RECORD types are deserialized to strongly-typed .NET classes.</span></span> <span data-ttu-id="8731a-106">Los campos de registro se representan como propiedades en la clase.</span><span class="sxs-lookup"><span data-stu-id="8731a-106">The record fields are represented as properties on the class.</span></span>  
  
 <span data-ttu-id="8731a-107">El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] admite los siguientes tipos de los tipos de registros:</span><span class="sxs-lookup"><span data-stu-id="8731a-107">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports the following kinds of RECORD types:</span></span>  
  
- <span data-ttu-id="8731a-108">Tipos de registros que se declaran como parámetros de tipo de fila de tabla % en procedimientos almacenados y funciones.</span><span class="sxs-lookup"><span data-stu-id="8731a-108">RECORD types that are declared as TABLE%ROWTYPE parameters in stored procedures and functions.</span></span>  
  
- <span data-ttu-id="8731a-109">Tipos de registros que se declaran como parámetros de tipo de registro en los paquetes de PL/SQL, por ejemplo, `TYPE rec_type1 IS RECORD(name varchar2(100), age number(3));`</span><span class="sxs-lookup"><span data-stu-id="8731a-109">RECORD types that are declared as TYPE of RECORD parameters in PL/SQL packages for example, `TYPE rec_type1 IS RECORD(name varchar2(100), age number(3));`</span></span>  
  
- <span data-ttu-id="8731a-110">Tipos de registros que contienen registros anidados.</span><span class="sxs-lookup"><span data-stu-id="8731a-110">RECORD types that contain nested records.</span></span>  
  
- <span data-ttu-id="8731a-111">Tipos de registros que aparecen como IN, OUT o IN OUT parámetros a procedimientos o funciones.</span><span class="sxs-lookup"><span data-stu-id="8731a-111">RECORD types that appear as IN, OUT, or IN OUT parameters to procedures or functions.</span></span>  
  
- <span data-ttu-id="8731a-112">Tipos de registros que son los valores devueltos de funciones.</span><span class="sxs-lookup"><span data-stu-id="8731a-112">RECORD types that are RETURN values of functions.</span></span>  
  
  <span data-ttu-id="8731a-113">En este tema se muestra cómo se representan los tipos de registros en el modelo de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="8731a-113">This topic shows how RECORD types are represented in the WCF service model.</span></span> <span data-ttu-id="8731a-114">Para obtener información acerca de cómo llamar a funciones y procedimientos de Oracle, vea [invocar funciones y procedimientos de la base de datos de Oracle mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md).</span><span class="sxs-lookup"><span data-stu-id="8731a-114">For information about how to call Oracle procedures and functions, see [Invoke Functions and Procedures in Oracle Database using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="8731a-115">Acerca de los ejemplos usados en este tema.</span><span class="sxs-lookup"><span data-stu-id="8731a-115">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="8731a-116">Los ejemplos de este tema usan el paquete PL/SQL de Oracle de SCOTT/ACCOUNT_PKG.</span><span class="sxs-lookup"><span data-stu-id="8731a-116">The examples in this topic use the /SCOTT/ACCOUNT_PKG Oracle PL/SQL PACKAGE.</span></span> <span data-ttu-id="8731a-117">Los elementos siguientes se usan desde ACCOUNT_PKG.</span><span class="sxs-lookup"><span data-stu-id="8731a-117">The following elements are used from ACCOUNT_PKG.</span></span>  
  
```  
TYPE address_rec_type IS RECORD (street customer.street%TYPE, city customer.city%TYPE, state customer.state%TYPE);  
  
FUNCTION create_account(acct IN ACCOUNT%ROWTYPE, addr IN address_rec_type) RETURN NUMBER;  
  
TYPE acctinfo_rec_type IS RECORD (acct account%ROWTYPE, address address_rec_type);  
  
FUNCTION get_accountinfo(aid NUMBER) RETURN acctinfo_rec_type;  
```  
  
 <span data-ttu-id="8731a-118">Una secuencia de comandos para generar este paquete se suministra con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="8731a-118">A script to generate this package is supplied with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] samples.</span></span> <span data-ttu-id="8731a-119">Para obtener más información, consulte la secuencia de comandos</span><span class="sxs-lookup"><span data-stu-id="8731a-119">For more information, see the script</span></span>  
  
 <span data-ttu-id="8731a-120">Para obtener más información acerca de los ejemplos, vea [ejemplos de adaptadores](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8731a-120">For more information about the samples, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
## <a name="record-types-in-the-wcf-service-model"></a><span data-ttu-id="8731a-121">Tipos de registros en el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="8731a-121">RECORD Types in the WCF Service Model</span></span>  
 <span data-ttu-id="8731a-122">Tipos de registros de Oracle se representan como tipos XML complejos mediante el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8731a-122">Oracle RECORD types are represented as complex XML types by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="8731a-123">En el modelo de servicio WCF, tipos complejos de XML se representan mediante una clase y las propiedades de esta clase representan los campos del tipo de registro de Oracle.</span><span class="sxs-lookup"><span data-stu-id="8731a-123">In the WCF service model, complex XML types are represented by a class, and the properties of this class represent the fields of the Oracle RECORD type.</span></span> <span data-ttu-id="8731a-124">La clase que representa un parámetro de tipo de registro se genera en un espacio de nombres se califica con el paquete (si existe) y el esquema de la función o procedimiento.</span><span class="sxs-lookup"><span data-stu-id="8731a-124">The class that represents a RECORD type parameter is generated in a namespace that is qualified by the PACKAGE (if any) and SCHEMA of the function or procedure.</span></span> <span data-ttu-id="8731a-125">Este espacio de nombres identifica la función o procedimiento del parámetro.</span><span class="sxs-lookup"><span data-stu-id="8731a-125">This namespace uniquely identifies the function or procedure of the parameter.</span></span> <span data-ttu-id="8731a-126">Por ejemplo, los parámetros de tipo de registro al procedimiento CREATE_ACCOUNT el ACCOUNT_PKG del paquete de Oracle se crean en el espacio de nombres siguiente: `microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT`.</span><span class="sxs-lookup"><span data-stu-id="8731a-126">For example, the RECORD type parameters to the CREATE_ACCOUNT procedure in the Oracle PACKAGE ACCOUNT_PKG are created in the following namespace: `microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT`.</span></span> <span data-ttu-id="8731a-127">Para obtener más información acerca de los espacios de nombres utilizados en el modelo de servicio WCF para representar tipos complejos en los procedimientos y funciones, vea [invocar funciones y procedimientos de la base de datos de Oracle mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md).</span><span class="sxs-lookup"><span data-stu-id="8731a-127">For more information about the namespaces used in the WCF service model to represent complex types in procedures and functions, see [Invoke Functions and Procedures in Oracle Database using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
 <span data-ttu-id="8731a-128">Mientras que el espacio de nombres de un parámetro de tipo de registro está determinado por el procedimiento o función, el nombre de la clase generada por el parámetro de tipo de registro se determina a la forma en que se declara el tipo de registro.</span><span class="sxs-lookup"><span data-stu-id="8731a-128">While the namespace of a RECORD type parameter is determined by the procedure or function, the name of the class generated for the RECORD type parameter is determined by the way in which the RECORD type is declared.</span></span> <span data-ttu-id="8731a-129">En la tabla siguiente muestra cómo se genera el nombre de la clase basada en las dos maneras diferentes de declarar el parámetro de tipo de registro de Oracle.</span><span class="sxs-lookup"><span data-stu-id="8731a-129">The following table shows how the name of the class is generated based on the two different ways of declaring the Oracle RECORD type parameter.</span></span>  
  
|<span data-ttu-id="8731a-130">Tipo de registro de Oracle</span><span class="sxs-lookup"><span data-stu-id="8731a-130">Oracle RECORD type</span></span>|<span data-ttu-id="8731a-131">Nombre</span><span class="sxs-lookup"><span data-stu-id="8731a-131">Name</span></span>|<span data-ttu-id="8731a-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8731a-132">Example</span></span>|  
|------------------------|----------|-------------|  
|<span data-ttu-id="8731a-133">Parámetro de procedimiento o función de la ROWTYPE del % tabla</span><span class="sxs-lookup"><span data-stu-id="8731a-133">TABLE%ROWTYPE procedure or function parameter</span></span>|<span data-ttu-id="8731a-134">[NOMBRE DE PARÁMETRO] REGISTRO</span><span class="sxs-lookup"><span data-stu-id="8731a-134">[PARAMETER_NAME]RECORD</span></span>|<span data-ttu-id="8731a-135">ACCTRECORD</span><span class="sxs-lookup"><span data-stu-id="8731a-135">ACCTRECORD</span></span>|  
|<span data-ttu-id="8731a-136">TIPO de parámetro de paquete de registro</span><span class="sxs-lookup"><span data-stu-id="8731a-136">TYPE of RECORD package parameter</span></span>|<span data-ttu-id="8731a-137">[NOMBRE_DEL_PAQUETE] [RECORD_TYPE_NAME] REGISTRO</span><span class="sxs-lookup"><span data-stu-id="8731a-137">[PACKAGE_NAME][RECORD_TYPE_NAME]RECORD</span></span>|<span data-ttu-id="8731a-138">ACCOUNT_PKGACCTINFO_REC_TYPERECORD</span><span class="sxs-lookup"><span data-stu-id="8731a-138">ACCOUNT_PKGACCTINFO_REC_TYPERECORD</span></span>|  
  
 <span data-ttu-id="8731a-139">[PARAMETER_NAME] = el nombre del parámetro de procedimiento o función; Por ejemplo, Acct.</span><span class="sxs-lookup"><span data-stu-id="8731a-139">[PARAMETER_NAME] = the name of the procedure or function parameter; for example, ACCT.</span></span>  
  
 <span data-ttu-id="8731a-140">[Nombre_del_paquete] = el nombre del paquete de Oracle.</span><span class="sxs-lookup"><span data-stu-id="8731a-140">[PACKAGE_NAME] = the name of the Oracle package.</span></span>  
  
 <span data-ttu-id="8731a-141">[RECORD_TYPE_NAME] = el nombre especificado en la declaración de tipo de registro; Por ejemplo, ACCTINFO_REC_TYPE.</span><span class="sxs-lookup"><span data-stu-id="8731a-141">[RECORD_TYPE_NAME] = the name specified in the RECORD TYPE declaration; for example, ACCTINFO_REC_TYPE.</span></span>  
  
 <span data-ttu-id="8731a-142">El código siguiente muestra las firmas de método del cliente WCF generado para dos funciones de Oracle.</span><span class="sxs-lookup"><span data-stu-id="8731a-142">The following code shows the method signatures of the WCF client generated for two Oracle functions.</span></span> <span data-ttu-id="8731a-143">La función /SCOTT/Package/ACCOUNT_PKG/CREATE_ACCOUNT toma dos parámetros de IN de tipo de registro simple y la función /SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNTINFO devuelve un parámetro de tipo de registro que contiene dos tipos de registro anidados.</span><span class="sxs-lookup"><span data-stu-id="8731a-143">The /SCOTT/Package/ACCOUNT_PKG/CREATE_ACCOUNT function takes two simple RECORD type IN parameters, and the /SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNTINFO function returns a RECORD type parameter that contains two nested RECORD types.</span></span> <span data-ttu-id="8731a-144">Las declaraciones de función de Oracle se incluyen en la parte superior del código.</span><span class="sxs-lookup"><span data-stu-id="8731a-144">The Oracle function declarations are included at the top of the code.</span></span> <span data-ttu-id="8731a-145">Los parámetros de cada función se califican con un espacio de nombres único.</span><span class="sxs-lookup"><span data-stu-id="8731a-145">The parameters of each function are qualified by a unique namespace.</span></span>  
  
```  
FUNCTION create_account(acct IN ACCOUNT%ROWTYPE, addr IN address_rec_type) RETURN NUMBER;  
FUNCTION get_accountinfo(aid NUMBER) RETURN acctinfo_rec_type;  
  
public partial class SCOTTPackageACCOUNT_PKGClient : System.ServiceModel.ClientBase<SCOTTPackageACCOUNT_PKG>, SCOTTPackageACCOUNT_PKG {  
  
    ...  
  
    public System.Nullable<decimal> CREATE_ACCOUNT(microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT.ACCTRECORD ACCT, microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.CREATE_ACCOUNT.ACCOUNT_PKGADDRESS_REC_TYPERECORD ADDR);  
  
    public microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACCOUNTINFO.ACCOUNT_PKGACCTINFO_REC_TYPERECORD GET_ACCOUNTINFO(System.Nullable<decimal> AID);  
}  
```  
  
 <span data-ttu-id="8731a-146">El código siguiente muestra las clases generadas para los parámetros de la función CREATE_ACCOUNT: `FUNCTION create_account(acct IN ACCOUNT%ROWTYPE, addr IN address_rec_type) RETURN NUMBER;`</span><span class="sxs-lookup"><span data-stu-id="8731a-146">The following code shows the classes generated for the parameters of the CREATE_ACCOUNT function: `FUNCTION create_account(acct IN ACCOUNT%ROWTYPE, addr IN address_rec_type) RETURN NUMBER;`</span></span>  
  
 <span data-ttu-id="8731a-147">Esta función tiene un parámetro declarado con un tipo de fila de tabla % y un parámetro declarado con un tipo de paquete de tipo de registro (`TYPE acctinfo_rec_type IS RECORD (acct account%ROWTYPE, address address_rec_type);`).</span><span class="sxs-lookup"><span data-stu-id="8731a-147">This function has a parameter declared with a TABLE%ROWTYPE and a parameter declared with a TYPE of RECORD package type (`TYPE acctinfo_rec_type IS RECORD (acct account%ROWTYPE, address address_rec_type);`).</span></span>  
  
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
  
### <a name="representation-of-a-simple-record-type"></a><span data-ttu-id="8731a-148">Representación de un tipo de registro Simple</span><span class="sxs-lookup"><span data-stu-id="8731a-148">Representation of a Simple Record Type</span></span>  
 <span data-ttu-id="8731a-149">El código siguiente muestra cómo se representa un tipo de registro simple en el modelo de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="8731a-149">The following code shows how a simple RECORD type is represented in the WCF service model.</span></span> <span data-ttu-id="8731a-150">Este código muestra la vista expandida de la **ACCOUNTRECORD** clase que representa el parámetro de tipo de fila % cuenta en la función CREATE_ACCOUNT.</span><span class="sxs-lookup"><span data-stu-id="8731a-150">This code shows the expanded view of the **ACCOUNTRECORD** class that represents the ACCOUNT%ROWTYPE parameter in the CREATE_ACCOUNT function.</span></span> <span data-ttu-id="8731a-151">En esta clase, los campos de registro (columnas de fila) se representan como propiedades.</span><span class="sxs-lookup"><span data-stu-id="8731a-151">In this class, the record fields (row columns) are represented as properties.</span></span>  
  
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
  
### <a name="representation-of-a-record-type-that-contains-nested-records"></a><span data-ttu-id="8731a-152">Representación de un tipo de registro que contiene registros anidados</span><span class="sxs-lookup"><span data-stu-id="8731a-152">Representation of a Record Type that Contains Nested Records</span></span>  
 <span data-ttu-id="8731a-153">El código siguiente muestra la representación de un tipo de registro que contiene registros anidados.</span><span class="sxs-lookup"><span data-stu-id="8731a-153">The following code shows the representation of a RECORD type that contains nested records.</span></span> <span data-ttu-id="8731a-154">Este tipo de registro determinado es el valor devuelto de la función GET_ACCOUNTINFO (`FUNCTION get_accountinfo(aid NUMBER) RETURN acctinfo_rec_type;`).</span><span class="sxs-lookup"><span data-stu-id="8731a-154">This particular RECORD type is the RETURN value of the GET_ACCOUNTINFO function (`FUNCTION get_accountinfo(aid NUMBER) RETURN acctinfo_rec_type;`).</span></span> <span data-ttu-id="8731a-155">El ACCTINFO_REC_TYPE es un parámetro de paquete que se declaran mediante la construcción de un tipo de registro (`TYPE acctinfo_rec_type IS RECORD (acct account%ROWTYPE, address address_rec_type);`).</span><span class="sxs-lookup"><span data-stu-id="8731a-155">The ACCTINFO_REC_TYPE is a package parameter declared using a TYPE of RECORD construct (`TYPE acctinfo_rec_type IS RECORD (acct account%ROWTYPE, address address_rec_type);`).</span></span> <span data-ttu-id="8731a-156">Contiene dos tipos de registros simple anidados, un registro de la fila de tabla % y un registro de tipo de registro del paquete.</span><span class="sxs-lookup"><span data-stu-id="8731a-156">It contains two nested simple record types, a TABLE%ROW record and a package TYPE of RECORD record.</span></span> <span data-ttu-id="8731a-157">Estos dos registros simple se declaran en el mismo espacio de nombres como su principal y siguen la convención de nomenclatura esperada.</span><span class="sxs-lookup"><span data-stu-id="8731a-157">These two simple records are declared in the same namespace as their parent record and follow the expected naming convention.</span></span>  
  
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
  
## <a name="using-record-types-in-your-code"></a><span data-ttu-id="8731a-158">Uso de tipos de registro en el código</span><span class="sxs-lookup"><span data-stu-id="8731a-158">Using RECORD Types in Your Code</span></span>  
 <span data-ttu-id="8731a-159">Uso de tipos de registros en el código es sencillo.</span><span class="sxs-lookup"><span data-stu-id="8731a-159">Using RECORD types in your code is straightforward.</span></span> <span data-ttu-id="8731a-160">Para invocar un procedimiento o función con un parámetro de tipo de registro, cree una instancia del tipo de registro o de tipos y pasarlo al método apropiado en el cliente WCF.</span><span class="sxs-lookup"><span data-stu-id="8731a-160">To invoke a procedure or function with a RECORD type parameter, you create an instance of the RECORD type or types and pass it to the appropriate method on the WCF client.</span></span> <span data-ttu-id="8731a-161">Cuando se devuelve el procedimiento o función, puede leer las propiedades de cualquier tipo de espera o función retorno o parámetros OUT en valores que se declaran como tipos de registros.</span><span class="sxs-lookup"><span data-stu-id="8731a-161">When the procedure or function returns, you can read properties on any OUT or IN OUT parameters or function RETURN values that are declared as RECORD types.</span></span> <span data-ttu-id="8731a-162">Para obtener más información acerca de cómo invocar procedimientos y funciones con el modelo de servicio WCF, vea [invocar funciones y procedimientos de la base de datos de Oracle mediante el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md).</span><span class="sxs-lookup"><span data-stu-id="8731a-162">For more information about how to invoke procedures and functions by using the WCF service model, see [Invoke Functions and Procedures in Oracle Database using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8731a-163">Parámetros de tipo de registro de Oracle (y devueltos de función) se califican con el espacio de nombres de su función o procedimiento (y paquete).</span><span class="sxs-lookup"><span data-stu-id="8731a-163">Oracle RECORD type parameters (and function returns) are qualified by the namespace of their function or procedure (and package).</span></span> <span data-ttu-id="8731a-164">Esto significa que un tipo de registro que se usa en dos procedimientos diferentes o funciones tendrá un espacio de nombres diferente para cada procedimiento o función.</span><span class="sxs-lookup"><span data-stu-id="8731a-164">This means that a RECORD type that is used in two different procedures or functions will have a different namespace for each procedure or function.</span></span> <span data-ttu-id="8731a-165">Debe ser seguro calificar el tipo de registro correctamente cuando se usa para una función o un procedimiento específico.</span><span class="sxs-lookup"><span data-stu-id="8731a-165">You must be sure to qualify the RECORD type correctly when you use it for a specific procedure or function.</span></span> <span data-ttu-id="8731a-166">Por ejemplo, un tipo de registro (declaración de tipo de registro) que se usa como un parámetro IN a dos funciones diferentes del paquete se declarará dos veces en el código de cliente WCF con cada declaración correspondiente al espacio de nombres único generado para cada función.</span><span class="sxs-lookup"><span data-stu-id="8731a-166">For example, a package RECORD type (RECORD of TYPE declaration) that is used as an IN parameter to two different functions will be declared twice in the WCF client code with each declaration corresponding to the unique namespace generated for each function.</span></span> <span data-ttu-id="8731a-167">Debe asegurarse de que utiliza el espacio de nombres correcto en el parámetro que se pasa a cada función respectivo.</span><span class="sxs-lookup"><span data-stu-id="8731a-167">You must be sure to use the correct namespace on the parameter that you pass to each respective function.</span></span>  
  
 <span data-ttu-id="8731a-168">En el ejemplo siguiente, se llama a la función CREATE_ACCOUNT con dos parámetros de registro simple.</span><span class="sxs-lookup"><span data-stu-id="8731a-168">In the following example, the CREATE_ACCOUNT function is called with two simple record parameters.</span></span> <span data-ttu-id="8731a-169">A continuación, se llama a la función GET_ACCOUNTINFO.</span><span class="sxs-lookup"><span data-stu-id="8731a-169">Next, the GET_ACCOUNTINFO function is called.</span></span> <span data-ttu-id="8731a-170">Esta función devuelve un tipo de registro que contiene registros anidados.</span><span class="sxs-lookup"><span data-stu-id="8731a-170">This function returns a RECORD type that contains nested records.</span></span> <span data-ttu-id="8731a-171">Seleccionar campo de valores de los registros devueltos se escriben en la consola.</span><span class="sxs-lookup"><span data-stu-id="8731a-171">Selected field values from the returned RECORD are written to the console.</span></span> <span data-ttu-id="8731a-172">Los pasos para establecer credenciales para la base de datos de Oracle y para abrir al cliente de WCF se omiten en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8731a-172">Steps to set credentials for the Oracle database and to open the WCF client are omitted from this example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8731a-173">Vea también</span><span class="sxs-lookup"><span data-stu-id="8731a-173">See Also</span></span>  
 [<span data-ttu-id="8731a-174">Desarrollar aplicaciones de base de datos de Oracle mediante el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="8731a-174">Develop Oracle Database applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)