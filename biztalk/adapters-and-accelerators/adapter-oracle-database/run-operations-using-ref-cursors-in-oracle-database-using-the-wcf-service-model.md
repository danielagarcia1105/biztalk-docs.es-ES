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
# <a name="run-operations-using-ref-cursors-in-oracle-database-using-the-wcf-service-model"></a><span data-ttu-id="52e8c-102">Ejecutar operaciones de uso de los cursores REF cursor en la base de datos de Oracle mediante el modelo de servicio de WCF</span><span class="sxs-lookup"><span data-stu-id="52e8c-102">Run Operations Using REF CURSORS in Oracle Database using the WCF Service Model</span></span>
<span data-ttu-id="52e8c-103">Un REF CURSOR es un tipo de datos de Oracle PL/SQL que representa un puntero a un conjunto de resultados en la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="52e8c-103">A REF CURSOR is an Oracle PL/SQL data type that represents a pointer to a result set in the Oracle database.</span></span> <span data-ttu-id="52e8c-104">El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] admite parámetros REF CURSOR en procedimientos, funciones y paquetes.</span><span class="sxs-lookup"><span data-stu-id="52e8c-104">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] supports REF CURSOR parameters in procedures, functions, and packages.</span></span> <span data-ttu-id="52e8c-105">Parámetros REF CURSOR pueden ser fuertemente tipado o débilmente tipada dependiendo de cómo se declaran en el procedimiento o función.</span><span class="sxs-lookup"><span data-stu-id="52e8c-105">REF CURSOR parameters can be strongly-typed or weakly-typed depending on how they are declared in the procedure or function.</span></span> <span data-ttu-id="52e8c-106">Para obtener una explicación detallada de cómo se representan los parámetros REF CURSOR mediante la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], consulte [esquemas de mensaje para los cursores REF cursor](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-ref-cursors.md). En la tabla siguiente se resume cómo se representan los parámetros REF CURSOR en el modelo de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="52e8c-106">For a detailed explanation of how REF CURSOR parameters are represented by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Message Schemas for REF CURSORS](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-ref-cursors.md).The following table summarizes how REF CURSOR parameters are represented in the WCF service model.</span></span>  
  
|<span data-ttu-id="52e8c-107">Dirección del parámetro</span><span class="sxs-lookup"><span data-stu-id="52e8c-107">Parameter Direction</span></span>|<span data-ttu-id="52e8c-108">Inflexible REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="52e8c-108">Strongly-typed REF CURSOR</span></span>|<span data-ttu-id="52e8c-109">Débilmente tipada REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="52e8c-109">Weakly-typed REF CURSOR</span></span>|  
|-------------------------|--------------------------------|------------------------------|  
|<span data-ttu-id="52e8c-110">IN</span><span class="sxs-lookup"><span data-stu-id="52e8c-110">IN</span></span>|`string [PARAM_NAME]`<br /><br /> <span data-ttu-id="52e8c-111">Cadena que contiene un bloque de PL/SQL.</span><span class="sxs-lookup"><span data-stu-id="52e8c-111">String that contains a PL/SQL block.</span></span> <span data-ttu-id="52e8c-112">El bloque de PL/SQL debe devolver un REF CURSOR abierto mediante la ejecución de una instrucción "Abrir para SELECT" o mediante la invocación de una función o procedimiento.</span><span class="sxs-lookup"><span data-stu-id="52e8c-112">The PL/SQL block must return an opened REF CURSOR either by executing an "OPEN FOR SELECT" statement or by invoking a function or procedure.</span></span> <span data-ttu-id="52e8c-113">Un signo de interrogación (?) indica la posición de REF CURSOR devuelto por el parámetro.</span><span class="sxs-lookup"><span data-stu-id="52e8c-113">A question mark (?) indicates the position of the REF CURSOR that returns the parameter.</span></span> <span data-ttu-id="52e8c-114">¿Por ejemplo, "BEGIN abierto?</span><span class="sxs-lookup"><span data-stu-id="52e8c-114">For example, "BEGIN OPEN ?</span></span> <span data-ttu-id="52e8c-115">SELECCIONE * DE MY_TABLE; END", o" BEGIN MY_PROC (PARM1,?, PARM2); FINALIZAR; ".</span><span class="sxs-lookup"><span data-stu-id="52e8c-115">FOR SELECT * FROM MY_TABLE; END", or "BEGIN MY_PROC(PARM1, ?, PARM2); END;".</span></span>|<span data-ttu-id="52e8c-116">Igual que fuertemente tipados</span><span class="sxs-lookup"><span data-stu-id="52e8c-116">Same as strongly-typed</span></span>|  
|<span data-ttu-id="52e8c-117">OUT</span><span class="sxs-lookup"><span data-stu-id="52e8c-117">OUT</span></span>|`out [PROC_NS].[PARAM_NAME]RECORD[] [PARAM_NAME]`<br /><br /> <span data-ttu-id="52e8c-118">Un conjunto de registros fuertemente tipada.</span><span class="sxs-lookup"><span data-stu-id="52e8c-118">A strongly-typed record set.</span></span>|`out [GENERIC_NS].GenRecordRow[] [PARAM_NAME]`<br /><br /> <span data-ttu-id="52e8c-119">Un débilmente tipada genérico conjunto de registros.</span><span class="sxs-lookup"><span data-stu-id="52e8c-119">A weakly-typed generic record set.</span></span>|  
|<span data-ttu-id="52e8c-120">EN ESPERA</span><span class="sxs-lookup"><span data-stu-id="52e8c-120">IN OUT</span></span>|<span data-ttu-id="52e8c-121">EN la salida de REF CURSOR parámetros se dividen en (IN) y un parámetro OUT.</span><span class="sxs-lookup"><span data-stu-id="52e8c-121">IN OUT REF CURSOR parameters are split into an IN and an OUT parameter.</span></span> <span data-ttu-id="52e8c-122">El parámetro IN se anexa "_IN" en la firma del método para distinguirlo del parámetro OUT.</span><span class="sxs-lookup"><span data-stu-id="52e8c-122">The IN parameter is appended with "_IN" in the method signature to distinguish it from the OUT parameter.</span></span> <span data-ttu-id="52e8c-123">El parámetro OUT se representa mediante un conjunto de registros fuertemente tipada.</span><span class="sxs-lookup"><span data-stu-id="52e8c-123">The OUT parameter is represented by a strongly-typed record set.</span></span><br /><br /> `string [PARAM_NAME]_IN`<br /><br /> `out [PROC_NS].[PARAM_NAME]RECORD[] [PARAM_NAME]`|<span data-ttu-id="52e8c-124">EN la salida de REF CURSOR parámetros se dividen en (IN) y un parámetro OUT.</span><span class="sxs-lookup"><span data-stu-id="52e8c-124">IN OUT REF CURSOR parameters are split into an IN and an OUT parameter.</span></span> <span data-ttu-id="52e8c-125">El parámetro IN se anexa "_IN" para distinguirlo del parámetro OUT.</span><span class="sxs-lookup"><span data-stu-id="52e8c-125">The IN parameter is appended with "_IN" to distinguish it from the OUT parameter.</span></span> <span data-ttu-id="52e8c-126">El parámetro OUT se representa mediante un conjunto de registros débilmente tipada.</span><span class="sxs-lookup"><span data-stu-id="52e8c-126">The OUT parameter is represented by a weakly-typed record set.</span></span><br /><br /> `string [PARAM_NAME]_IN`<br /><br /> `out [GENERIC_NS].GenRecordRow[] [PARAM_NAME]`|  
  
 <span data-ttu-id="52e8c-127">[PARAM_NAME] = el nombre del parámetro en la definición de función o un procedimiento en la base de datos de Oracle; Por ejemplo, MYREFCURSOR.</span><span class="sxs-lookup"><span data-stu-id="52e8c-127">[PARAM_NAME] = the name of the parameter in the function or procedure definition on the Oracle database; for example, MYREFCURSOR.</span></span>  
  
 <span data-ttu-id="52e8c-128">[PROC_NS] = el espacio de nombres único generado para que contenga los parámetros del paquete, procedimiento o función; Por ejemplo, "microsoft.lobservices.oracledb._2007._03.SCOTT. Package.ACCOUNT_PKG. GET_ACTIVITY".</span><span class="sxs-lookup"><span data-stu-id="52e8c-128">[PROC_NS] = The unique namespace generated to contain parameters of the package, procedure, or function; for example, "microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACTIVITY".</span></span>  
  
 <span data-ttu-id="52e8c-129">[GENERIC_NS] = el espacio de nombres en el que se define el conjunto de registros genérico, "microsoft.lobservices.oracledb._2007._03".</span><span class="sxs-lookup"><span data-stu-id="52e8c-129">[GENERIC_NS] = The namespace in which the generic record set is defined, "microsoft.lobservices.oracledb._2007._03".</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="52e8c-130">Acerca de los ejemplos usados en este tema</span><span class="sxs-lookup"><span data-stu-id="52e8c-130">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="52e8c-131">Los ejemplos de este tema usan el paquete de Oracle SCOTT/paquetes/ACCOUNT_PKG.</span><span class="sxs-lookup"><span data-stu-id="52e8c-131">The examples in this topic use the /SCOTT/Package/ACCOUNT_PKG Oracle PACKAGE.</span></span> <span data-ttu-id="52e8c-132">El siguiente procedimiento se utiliza desde ACCOUNT_PKG:</span><span class="sxs-lookup"><span data-stu-id="52e8c-132">The following procedure is used from ACCOUNT_PKG:</span></span>  
  
```  
PROCEDURE get_activity(inrecs IN SYS_REFCURSOR, status OUT NUMBER, inoutrecs IN OUT activity_ref_type, outrecs OUT SYS_REFCURSOR);  
```  
  
 <span data-ttu-id="52e8c-133">Una secuencia de comandos para generar este paquete se suministra con los ejemplos del SDK.</span><span class="sxs-lookup"><span data-stu-id="52e8c-133">A script to generate this package is supplied with the SDK samples.</span></span> <span data-ttu-id="52e8c-134">Para obtener más información acerca de los ejemplos SDK, vea [ejemplos del SDK](../../core/samples-in-the-sdk.md).</span><span class="sxs-lookup"><span data-stu-id="52e8c-134">For more information about the SDK samples, see [Samples in the SDK](../../core/samples-in-the-sdk.md).</span></span>  
  
## <a name="ref-cursor-parameters-in-the-wcf-service-model"></a><span data-ttu-id="52e8c-135">Parámetros REF CURSOR en el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="52e8c-135">REF CURSOR Parameters in the WCF Service Model</span></span>  
 <span data-ttu-id="52e8c-136">Los ejemplos siguientes muestran las clases y el cliente WCF generado para el procedimiento /SCOTT/Package/ACCOUNT_PKG/GET_ACTIVITY.</span><span class="sxs-lookup"><span data-stu-id="52e8c-136">The following examples show the classes and WCF client generated for the /SCOTT/Package/ACCOUNT_PKG/GET_ACTIVITY procedure.</span></span> <span data-ttu-id="52e8c-137">Este procedimiento se débilmente tipada IN y parámetros de salida de REF CURSOR y un parámetro de IN OUT REF CURSOR fuertemente tipada.</span><span class="sxs-lookup"><span data-stu-id="52e8c-137">This procedure has weakly-typed IN and OUT REF CURSOR parameters and a strongly-typed IN OUT REF CURSOR parameter.</span></span>  
  
 <span data-ttu-id="52e8c-138">Aquí está la firma del método que se genera en el cliente WCF para invocar GET_ACTIVITY.</span><span class="sxs-lookup"><span data-stu-id="52e8c-138">Here is the signature of the method that is generated in the WCF client to invoke GET_ACTIVITY.</span></span>  
  
```  
public System.Nullable<decimal> GET_ACTIVITY(string INRECS, string INOUTRECS_IN, out microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACTIVITY.INOUTRECSRECORD[] INOUTRECS, out microsoft.lobservices.oracledb._2007._03.GenRecordRow[] OUTRECS);  
```  
  
 <span data-ttu-id="52e8c-139">En el **GET_ACTIVITY**  /método siguiente, el parámetro IN OUT INOUTRECS se divide en dos parámetros:</span><span class="sxs-lookup"><span data-stu-id="52e8c-139">In the **GET_ACTIVITY** method, the IN OUT parameter INOUTRECS is split into two parameters:</span></span>  
  
-   <span data-ttu-id="52e8c-140">INOUTRECS_IN es una cadena que representa un parámetro IN REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="52e8c-140">INOUTRECS_IN is a string that represents an IN REF CURSOR parameter.</span></span>  
  
-   <span data-ttu-id="52e8c-141">INOUTRECS es un conjunto de registros fuertemente tipado que representa un parámetro de salida de REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="52e8c-141">INOUTRECS is a strongly-typed record set that represents an OUT REF CURSOR parameter.</span></span>  
  
 <span data-ttu-id="52e8c-142">El débilmente tipada parámetro OUT, OUTRECS, se representa como un conjunto de registros genérico.</span><span class="sxs-lookup"><span data-stu-id="52e8c-142">The weakly-typed OUT parameter, OUTRECS, is represented as a generic record set.</span></span> <span data-ttu-id="52e8c-143">El débilmente tipada en parámetro, INRECS, se representa como una cadena.</span><span class="sxs-lookup"><span data-stu-id="52e8c-143">The weakly-typed IN parameter, INRECS, is represented as a string.</span></span>  
  
### <a name="strongly-typed-out-ref-cursor-parameters"></a><span data-ttu-id="52e8c-144">Fuertemente tipadas REF CURSOR parámetros OUT</span><span class="sxs-lookup"><span data-stu-id="52e8c-144">Strongly-Typed OUT REF CURSOR Parameters</span></span>  
 <span data-ttu-id="52e8c-145">Inflexible OUT (o en espera) parámetros REF CURSOR se generan en un único espacio de nombres basado en el esquema, el paquete y el nombre del procedimiento o función en el que se utilizan.</span><span class="sxs-lookup"><span data-stu-id="52e8c-145">Strongly-typed OUT (or IN OUT) REF CURSOR parameters are generated in a unique namespace based on the SCHEMA, PACKAGE, and name of the procedure or function in which they are used.</span></span> <span data-ttu-id="52e8c-146">El procedimiento /SCOTT/Package/ACCOUNT_PKG/GET_ACTIVITY, este espacio de nombres es `microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACTIVITY`.</span><span class="sxs-lookup"><span data-stu-id="52e8c-146">For the /SCOTT/Package/ACCOUNT_PKG/GET_ACTIVITY procedure, this namespace is `microsoft.lobservices.oracledb._2007._03.SCOTT.Package.ACCOUNT_PKG.GET_ACTIVITY`.</span></span> <span data-ttu-id="52e8c-147">El nombre de clase se forma anexando el nombre del parámetro con "Registro a" y la clase se compone de las propiedades que representan los campos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="52e8c-147">The class name is formed by appending the name of the parameter with "RECORD" and the class is composed of properties that represent the Oracle fields.</span></span> <span data-ttu-id="52e8c-148">A continuación muestra una parte de la clase que representa los registros fuertemente tipado generados para el parámetro INOUTRECS REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="52e8c-148">The following shows a part of the class that represents the strongly-typed records generated for the INOUTRECS REF CURSOR parameter.</span></span>  
  
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
  
### <a name="weakly-typed-out-ref-cursor-parameters"></a><span data-ttu-id="52e8c-149">Débilmente tipada REF CURSOR parámetros OUT</span><span class="sxs-lookup"><span data-stu-id="52e8c-149">Weakly-Typed OUT REF CURSOR Parameters</span></span>  
 <span data-ttu-id="52e8c-150">Débilmente tipada OUT (o en espera) parámetros REF CURSOR se representan mediante la clase de registro genérico.</span><span class="sxs-lookup"><span data-stu-id="52e8c-150">Weakly-typed OUT (or IN OUT) REF CURSOR parameters are represented by the generic record class.</span></span> <span data-ttu-id="52e8c-151">El conjunto de registros genérico siempre se genera en el mismo espacio de nombres y con el mismo nombre de clase, independientemente de la función o procedimiento.</span><span class="sxs-lookup"><span data-stu-id="52e8c-151">The generic record set is always generated in the same namespace and with the same class name regardless of the function or procedure.</span></span> <span data-ttu-id="52e8c-152">El código siguiente muestra la clase de registro genérico, **microsoft.lobservices.oracledb._2007._03.GenRecordRow**, que representa los registros para el parámetro OUTRECS OUT SYS_REFCURSOR (débilmente tipada).</span><span class="sxs-lookup"><span data-stu-id="52e8c-152">The following code shows the generic record class, **microsoft.lobservices.oracledb._2007._03.GenRecordRow**, which represents the records for the OUTRECS OUT SYS_REFCURSOR parameter (weakly-typed).</span></span>  
  
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
  
## <a name="using-ref-cursor-parameters-with-a-wcf-client"></a><span data-ttu-id="52e8c-153">Usar parámetros REF CURSOR con un cliente de WCF</span><span class="sxs-lookup"><span data-stu-id="52e8c-153">Using REF CURSOR Parameters with a WCF Client</span></span>  
 <span data-ttu-id="52e8c-154">Para invocar un procedimiento o función con parámetros REF CURSOR mediante un cliente WCF, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="52e8c-154">To invoke a procedure or function with REF CURSOR parameters by using a WCF client, you do the following:</span></span>  
  
1.  <span data-ttu-id="52e8c-155">Pasar una cadena para cada uno en o bloquear el parámetro OUT en REF CURSOR que contiene el código de PL/SQL para abrir el REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="52e8c-155">Pass a string for each IN or IN OUT REF CURSOR parameter that contains the PL/SQL block to open the REF CURSOR.</span></span> <span data-ttu-id="52e8c-156">Este bloque puede ejecutar una instrucción Abrir para SELECT o invocar una función o procedimiento que devuelve un REF CURSOR abierto en un parámetro OUT.</span><span class="sxs-lookup"><span data-stu-id="52e8c-156">This block can either execute an OPEN FOR SELECT statement or invoke a function or procedure that returns an opened REF CURSOR in an OUT parameter.</span></span>  
  
2.  <span data-ttu-id="52e8c-157">Cuando finaliza el procedimiento o función, trabajar con los datos en los conjuntos de registros devueltos para cualquier OUT o IN OUT REF CURSOR parámetros.</span><span class="sxs-lookup"><span data-stu-id="52e8c-157">When the procedure or function returns, operate on the data in the record sets returned for any OUT or IN OUT REF CURSOR parameters.</span></span> <span data-ttu-id="52e8c-158">El conjunto de registros será un conjunto de los parámetros REF CURSOR débilmente tipada de registros genérico o un conjunto para los parámetros REF CURSOR fuertemente tipada de registros fuertemente tipada.</span><span class="sxs-lookup"><span data-stu-id="52e8c-158">The record set will be a generic record set for weakly-typed REF CURSOR parameters or a strongly-typed record set for strongly-typed REF CURSOR parameters.</span></span>  
  
 <span data-ttu-id="52e8c-159">Para obtener más información sobre cómo invocar los procedimientos y funciones mediante el modelo de servicio WCF, vea [invocar funciones y procedimientos de la base de datos de Oracle mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md).</span><span class="sxs-lookup"><span data-stu-id="52e8c-159">For more information about how to invoke procedures and functions by using the WCF service model, see [Invoke Functions and Procedures in Oracle Database using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/invoke-functions-and-procedures-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
 <span data-ttu-id="52e8c-160">En el ejemplo siguiente se llama al procedimiento GET_ACTIVITY.</span><span class="sxs-lookup"><span data-stu-id="52e8c-160">The following example calls the GET_ACTIVITY procedure.</span></span> <span data-ttu-id="52e8c-161">Muestra dos formas de especificar un parámetro IN REF CURSOR:</span><span class="sxs-lookup"><span data-stu-id="52e8c-161">It demonstrates both ways of specifying an IN REF CURSOR parameter:</span></span>  
  
-   <span data-ttu-id="52e8c-162">Para el parámetro en REF CURSOR, se especifica una instrucción Abrir para SELECT para devolver la actividad para 100001 de cuenta.</span><span class="sxs-lookup"><span data-stu-id="52e8c-162">For the IN REF CURSOR parameter, an OPEN FOR SELECT statement is specified to return activity for ACCOUNT 100001.</span></span>  
  
-   <span data-ttu-id="52e8c-163">Para el parámetro OUT en REF CURSOR, se invoca el procedimiento /SCOTT/Package/ACCOUNT_PKG/GET_ALL_ACTIVITY.</span><span class="sxs-lookup"><span data-stu-id="52e8c-163">For the IN OUT REF CURSOR parameter, the /SCOTT/Package/ACCOUNT_PKG/GET_ALL_ACTIVITY procedure is invoked.</span></span> <span data-ttu-id="52e8c-164">Este procedimiento abre un REF CURSOR que contiene toda la actividad en la tabla ACCOUNTACTIVITY y lo devuelve como un parámetro OUT.</span><span class="sxs-lookup"><span data-stu-id="52e8c-164">This procedure opens a REF CURSOR that contains all of the activity in the ACCOUNTACTIVITY table and returns it as an OUT parameter.</span></span>  
  
 <span data-ttu-id="52e8c-165">El ejemplo también muestra cómo leer datos desde el conjunto devuelto para los parámetros REF CURSOR fuertemente tipado tanto débilmente tipada de registros.</span><span class="sxs-lookup"><span data-stu-id="52e8c-165">The example also demonstrates how to read data from the record set returned for both strongly-typed and weakly-typed REF CURSOR parameters.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="52e8c-166">Vea también</span><span class="sxs-lookup"><span data-stu-id="52e8c-166">See Also</span></span>  
 [<span data-ttu-id="52e8c-167">Desarrollar aplicaciones de bases de datos de Oracle mediante el modelo de servicio WCF</span><span class="sxs-lookup"><span data-stu-id="52e8c-167">Develop Oracle Database Application Using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)