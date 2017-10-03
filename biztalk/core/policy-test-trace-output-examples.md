---
title: Ejemplos del resultado de seguimiento de pruebas de directivas | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- testing, policies
- policies, testing
- testing, examples
ms.assetid: 92e1dc7f-1a8d-41a5-84b6-46d5ad9f2ef2
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e3678769dffa03bb77c3e86fef02998a354b1fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="policy-test-trace-output-examples"></a>Ejemplos del resultado del seguimiento de pruebas de directivas
Esta sección contiene ejemplos de salida de pruebas de directivas para diferentes tipos de hechos.  
  
## <a name="net-class"></a>Clase .Net  
 Regla de ejemplo "TestRule1" en la directiva "LoanProcessing":  
  
```  
IF test.get_ID > 0  
THEN <do something>  
```  
  
 **Resultado:**  
  
 SEGUIMIENTO de motor de reglas para conjunto de reglas: LoanProcessing 3/16/2004 9:50:28 A.M.  
  
 ACTIVIDAD DE DATOS 3/16/2004 9:50:28 A.M.  
  
 Identificador de la instancia de motor de reglas: 9effe3f9-d3ad-4125-99fa-56bb379188f7  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Operación: Assert  
  
 Tipo de objeto: MyTest.test  
  
 Identificador de instancia de objeto: 872  
  
 PRUEBA DE EVALUACIÓN DE CONDICIÓN (COINCIDENCIA) 3/16/2004 9:50:28 A.M.  
  
 Identificador de la instancia de motor de reglas: 9effe3f9-d3ad-4125-99fa-56bb379188f7  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Expresión de prueba: MyTest.test.get_ID > 0  
  
 Deja el valor del operando: 100  
  
 Valor del operando de la derecha: 0  
  
 Resultado de pruebas: True  
  
 ACTUALIZACIÓN DE AGENDA 3/16/2004 9:50:28 A.M.  
  
 Identificador de la instancia de motor de reglas: 9effe3f9-d3ad-4125-99fa-56bb379188f7  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Operación: agregar  
  
 Nombre de regla: TestRule1  
  
 Criterios de resolución de conflictos: 0  
  
 REGLA ACTIVADA 3/16/2004 9:50:28 A.M.  
  
 Identificador de la instancia de motor de reglas: 9effe3f9-d3ad-4125-99fa-56bb379188f7  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Nombre de regla: TestRule1  
  
 Criterios de resolución de conflictos: 0  
  
 ACTIVIDAD DE DATOS 3/16/2004 9:50:28 A.M.  
  
 Identificador de la instancia de motor de reglas: 9effe3f9-d3ad-4125-99fa-56bb379188f7  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Operación: retirar  
  
 Tipo de objeto: MyTest.test  
  
 Identificador de instancia de objeto: 872  
  
## <a name="dataconnectiontypeddatarow"></a>DataConnection/TypedDataRow  
 Regla de ejemplo "TestRule1" en la directiva "LoanProcessing":  
  
```  
IF NorthWind.CustInfo.CreditCardBalance > 0  
THEN <do something>  
```  
  
 **Resultado:**  
  
 SEGUIMIENTO de motor de reglas para conjunto de reglas: LoanProcessing 3/16/2004 8:30:16 AM  
  
 ACTIVIDAD DE DATOS 3/16/2004 8:30:16 AM  
  
 Identificador de la instancia de motor de reglas: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Operación: Assert  
  
 Tipo de objeto: DataConnection:Northwind:CustInfo  
  
 Identificador de instancia de objeto: 874  
  
 PRUEBA DE EVALUACIÓN DE CONDICIÓN (COINCIDENCIA) 3/16/2004 8:30:16 AM  
  
 Identificador de la instancia de motor de reglas: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Expresión de prueba: seleccione * de [CustInfo] donde [CreditCardBalance] > 0  
  
 Valor del operando izquierdo:  
  
 Valor del operando derecho:  
  
 Resultado de pruebas: True  
  
 ACTIVIDAD DE DATOS 3/16/2004 8:30:16 AM  
  
 Identificador de la instancia de motor de reglas: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Operación: Assert  
  
 Tipo de objeto: TypedDataRow:Northwind:CustInfo  
  
 Identificador de instancia de objeto: 177556  
  
 ACTUALIZACIÓN DE AGENDA 3/16/2004 8:30:16 AM  
  
 Identificador de la instancia de motor de reglas: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Operación: agregar  
  
 Nombre de regla: TestRule1  
  
 Criterios de resolución de conflictos: 0  
  
 ACTIVIDAD DE DATOS 3/16/2004 8:30:16 AM  
  
 Identificador de la instancia de motor de reglas: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Operación: Assert  
  
 Tipo de objeto: TypedDataRow:Northwind:CustInfo  
  
 Identificador de instancia de objeto: 177559  
  
 ACTUALIZACIÓN DE AGENDA 3/16/2004 8:30:16 AM  
  
 Identificador de la instancia de motor de reglas: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Operación: agregar  
  
 Nombre de regla: TestRule1  
  
 Criterios de resolución de conflictos: 0  
  
 ACTIVIDAD DE DATOS 3/16/2004 8:30:16 AM  
  
 Identificador de la instancia de motor de reglas: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Operación: Assert  
  
 Tipo de objeto: TypedDataRow:Northwind:CustInfo  
  
 Identificador de instancia de objeto: 177558  
  
 ACTUALIZACIÓN DE AGENDA 3/16/2004 8:30:16 AM  
  
 Identificador de la instancia de motor de reglas: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Operación: agregar  
  
 Nombre de regla: TestRule1  
  
 Criterios de resolución de conflictos: 0  
  
 REGLA ACTIVADA 3/16/2004 8:30:16 AM  
  
 Identificador de la instancia de motor de reglas: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Nombre de regla: TestRule1  
  
 Criterios de resolución de conflictos: 0  
  
 REGLA ACTIVADA 3/16/2004 8:30:16 AM  
  
 Identificador de la instancia de motor de reglas: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Nombre de regla: TestRule1  
  
 Criterios de resolución de conflictos: 0  
  
 REGLA ACTIVADA 3/16/2004 8:30:16 AM  
  
 Identificador de la instancia de motor de reglas: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Nombre de regla: TestRule1  
  
 Criterios de resolución de conflictos: 0  
  
 ACTIVIDAD DE DATOS 3/16/2004 8:30:16 AM  
  
 Identificador de la instancia de motor de reglas: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Operación: retirar  
  
 Tipo de objeto: DataConnection:Northwind:CustInfo  
  
 Identificador de instancia de objeto: 874  
  
 ACTIVIDAD DE DATOS 3/16/2004 8:30:16 AM  
  
 Identificador de la instancia de motor de reglas: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Operación: retirar  
  
 Tipo de objeto: TypedDataRow:Northwind:CustInfo  
  
 Identificador de instancia de objeto: 177559  
  
 ACTIVIDAD DE DATOS 3/16/2004 8:30:16 AM  
  
 Identificador de la instancia de motor de reglas: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Operación: retirar  
  
 Tipo de objeto: TypedDataRow:Northwind:CustInfo  
  
 Identificador de instancia de objeto: 177558  
  
 ACTIVIDAD DE DATOS 3/16/2004 8:30:16 AM  
  
 Identificador de la instancia de motor de reglas: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Operación: retirar  
  
 Tipo de objeto: TypedDataRow:Northwind:CustInfo  
  
 Identificador de instancia de objeto: 177556  
  
 En el ejemplo anterior se indica que tres filas de la tabla CustInfo cumplen la condición de la regla.  Por eso hubo que imponer únicamente tres TypedDataRows en el motor y se produjo una actualización de agenda y activación de reglas para cada instancia.  
  
## <a name="typedatatabletypeddatarow"></a>TypeDataTable/TypedDataRow  
 Regla de ejemplo "TestRule1" en la directiva "LoanProcessing":  
  
```  
IF NorthWind.CustInfo.CreditCardBalance > 0  
THEN <do something>  
```  
  
 **Resultado:**  
  
 SEGUIMIENTO de motor de reglas para conjunto de reglas: LoanProcessing 3/17/2004 11:27:35 AM  
  
 ACTIVIDAD DE DATOS 3/17/2004 11:27:35 AM  
  
 Identificador de la instancia de motor de reglas: 0f7bcdf3-8103-4990-a740-acaeee386439  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Operación: Assert  
  
 Tipo de objeto: TypedDataTable:Northwind:CustInfo  
  
 Identificador de instancia de objeto: 377  
  
 ACTIVIDAD DE DATOS 3/17/2004 11:27:35 AM  
  
 Identificador de la instancia de motor de reglas: 0f7bcdf3-8103-4990-a740-acaeee386439  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Operación: Assert  
  
 Tipo de objeto: TypedDataRow:Northwind:CustInfo  
  
 Identificador de instancia de objeto: 376  
  
 PRUEBA DE EVALUACIÓN DE CONDICIÓN (COINCIDENCIA) 3/17/2004 11:27:35 AM  
  
 Identificador de la instancia de motor de reglas: 0f7bcdf3-8103-4990-a740-acaeee386439  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Expresión de prueba: TypedDataRow:Northwind:CustInfo.CreditCardBalance > 0  
  
 Deja el valor del operando: 500  
  
 Valor del operando de la derecha: 0  
  
 Resultado de pruebas: True  
  
 ACTUALIZACIÓN DE AGENDA 3/17/2004 11:27:35 AM  
  
 Identificador de la instancia de motor de reglas: 0f7bcdf3-8103-4990-a740-acaeee386439  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Operación: agregar  
  
 Nombre de regla: TestRule1  
  
 Criterios de resolución de conflictos: 0  
  
 ACTIVIDAD DE DATOS 3/17/2004 11:27:35 AM  
  
 Identificador de la instancia de motor de reglas: 0f7bcdf3-8103-4990-a740-acaeee386439  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Operación: Assert  
  
 Tipo de objeto: TypedDataRow:Northwind:CustInfo  
  
 Identificador de instancia de objeto: 375  
  
 PRUEBA DE EVALUACIÓN DE CONDICIÓN (COINCIDENCIA) 3/17/2004 11:27:35 AM  
  
 Identificador de la instancia de motor de reglas: 0f7bcdf3-8103-4990-a740-acaeee386439  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Expresión de prueba: TypedDataRow:Northwind:CustInfo.CreditCardBalance > 0  
  
 Deja el valor del operando: 1000  
  
 Valor del operando de la derecha: 0  
  
 Resultado de pruebas: True  
  
 ACTUALIZACIÓN DE AGENDA 3/17/2004 11:27:35 AM  
  
 Identificador de la instancia de motor de reglas: 0f7bcdf3-8103-4990-a740-acaeee386439  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Operación: agregar  
  
 Nombre de regla: TestRule1  
  
 Criterios de resolución de conflictos: 0  
  
 ACTIVIDAD DE DATOS 3/17/2004 11:27:35 AM  
  
 Identificador de la instancia de motor de reglas: 0f7bcdf3-8103-4990-a740-acaeee386439  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Operación: Assert  
  
 Tipo de objeto: TypedDataRow:Northwind:CustInfo  
  
 Identificador de instancia de objeto: 374  
  
 PRUEBA DE EVALUACIÓN DE CONDICIÓN (COINCIDENCIA) 3/17/2004 11:27:35 AM  
  
 Identificador de la instancia de motor de reglas: 0f7bcdf3-8103-4990-a740-acaeee386439  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Expresión de prueba: TypedDataRow:Northwind:CustInfo.CreditCardBalance > 0  
  
 Deja el valor del operando: 35000  
  
 Valor del operando de la derecha: 0  
  
 Resultado de pruebas: True  
  
 ACTUALIZACIÓN DE AGENDA 3/17/2004 11:27:35 AM  
  
 Identificador de la instancia de motor de reglas: 0f7bcdf3-8103-4990-a740-acaeee386439  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Operación: agregar  
  
 Nombre de regla: TestRule1  
  
 Criterios de resolución de conflictos: 0  
  
 REGLA ACTIVADA 3/17/2004 11:27:35 AM  
  
 Identificador de la instancia de motor de reglas: 0f7bcdf3-8103-4990-a740-acaeee386439  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Nombre de regla: TestRule1  
  
 Criterios de resolución de conflictos: 0  
  
 REGLA ACTIVADA 3/17/2004 11:27:35 AM  
  
 Identificador de la instancia de motor de reglas: 0f7bcdf3-8103-4990-a740-acaeee386439  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Nombre de regla: TestRule1  
  
 Criterios de resolución de conflictos: 0  
  
 REGLA ACTIVADA 3/17/2004 11:27:35 AM  
  
 Identificador de la instancia de motor de reglas: 0f7bcdf3-8103-4990-a740-acaeee386439  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Nombre de regla: TestRule1  
  
 Criterios de resolución de conflictos: 0  
  
 ACTIVIDAD DE DATOS 3/17/2004 11:27:35 AM  
  
 Identificador de la instancia de motor de reglas: 0f7bcdf3-8103-4990-a740-acaeee386439  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Operación: retirar  
  
 Tipo de objeto: TypedDataTable:Northwind:CustInfo  
  
 Identificador de instancia de objeto: 377  
  
 ACTIVIDAD DE DATOS 3/17/2004 11:27:35 AM  
  
 Identificador de la instancia de motor de reglas: 0f7bcdf3-8103-4990-a740-acaeee386439  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Operación: retirar  
  
 Tipo de objeto: TypedDataRow:Northwind:CustInfo  
  
 Identificador de instancia de objeto: 375  
  
 ACTIVIDAD DE DATOS 3/17/2004 11:27:35 AM  
  
 Identificador de la instancia de motor de reglas: 0f7bcdf3-8103-4990-a740-acaeee386439  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Operación: retirar  
  
 Tipo de objeto: TypedDataRow:Northwind:CustInfo  
  
 Identificador de instancia de objeto: 374  
  
 ACTIVIDAD DE DATOS 3/17/2004 11:27:35 AM  
  
 Identificador de la instancia de motor de reglas: 0f7bcdf3-8103-4990-a740-acaeee386439  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Operación: retirar  
  
 Tipo de objeto: TypedDataRow:Northwind:CustInfo  
  
 Identificador de instancia de objeto: 376  
  
> [!NOTE]
>  En el ejemplo anterior se muestra que TypedDataTable contenía tres filas y todas estaban declaradas como TypedDataRow.  Todas se evaluaron como True en la condición, lo que hizo que la regla se agregara a la agenda y se activara.  
  
## <a name="typedxmldocument"></a>TypedXmlDocument  
 Regla de ejemplo "TestRule1" en la directiva "LoanProcessing":  
  
```  
IF Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType.TimeInMonths >= 4  
THEN <do something>  
```  
  
 **Resultado:**  
  
 SEGUIMIENTO de motor de reglas para conjunto de reglas: LoanProcessing 3/17/2004 9:23:05 AM  
  
 ACTIVIDAD DE DATOS 3/17/2004 9:23:05 AM  
  
 Identificador de la instancia de motor de reglas: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Operación: Assert  
  
 Tipo de objeto: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case  
  
 Identificador de instancia de objeto: 858  
  
 ACTIVIDAD DE DATOS 3/17/2004 9:23:05 AM  
  
 Identificador de la instancia de motor de reglas: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Operación: Assert  
  
 Tipo de objeto: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType  
  
 Identificador de instancia de objeto: 853  
  
 PRUEBA DE EVALUACIÓN DE CONDICIÓN (COINCIDENCIA) 3/17/2004 9:23:05 AM  
  
 Identificador de la instancia de motor de reglas: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Expresión de prueba: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType.TimeInMonths > = 4  
  
 Deja el valor del operando: 6  
  
 Valor del operando de la derecha: 4  
  
 Resultado de pruebas: True  
  
 ACTUALIZACIÓN DE AGENDA 3/17/2004 9:23:05 AM  
  
 Identificador de la instancia de motor de reglas: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Operación: agregar  
  
 Nombre de regla: TestRule1  
  
 Criterios de resolución de conflictos: 0  
  
 REGLA ACTIVADA 3/17/2004 9:23:05 AM  
  
 Identificador de la instancia de motor de reglas: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Nombre de regla: TestRule1  
  
 Criterios de resolución de conflictos: 0  
  
 ACTIVIDAD DE DATOS 3/17/2004 9:23:05 AM  
  
 Identificador de la instancia de motor de reglas: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Operación: retirar  
  
 Tipo de objeto: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case  
  
 Identificador de instancia de objeto: 858  
  
 ACTIVIDAD DE DATOS 3/17/2004 9:23:05 AM  
  
 Identificador de la instancia de motor de reglas: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b  
  
 Nombre de conjunto de reglas: LoanProcessing  
  
 Operación: retirar  
  
 Tipo de objeto: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType  
  
 Identificador de instancia de objeto: 853  
  
 Este ejemplo muestra que un **TypedXmlDocument** se imponen en el motor con un tipo de documento de "Microsoft.Samples.BizTalk.LoansProcessor.Case".  En función del selector XPath definido en la regla, el motor creó y declaró un TypedXmlDocument secundario con el tipo "Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType" basado en el tipo de documento y la cadena de selector.  
  
 Dado que este TypedXmlDocument secundario fue evaluado como True en la condición, se originó una actualización de agenda y activación de reglas.  El elemento primario y el secundario **TypedXmlDocument**del, a continuación, se retiraron.  
  
## <a name="update-function"></a>Función Update  
 Directiva de ejemplo "Order"  
  
 **Regla "InventoryCheck"**  
  
```  
IF Inventory.AllocateInventory == True  
THEN Order.inventoryAvailable == True  
   Update(Order)  
```  
  
 **Regla "Ship"**  
  
```  
IF Order.inventoryAvailable == True  
THEN Shipment.ShipOrder  
```  
  
 **Resultado:**  
  
 SEGUIMIENTO de motor de reglas para conjunto de reglas: ordenar 3/17/2004 10:31:17 AM  
  
 ACTIVIDAD DE DATOS 3/17/2004 10:31:17 AM  
  
 Identificador de la instancia de motor de reglas: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 Nombre de conjunto de reglas: orden  
  
 Operación: Assert  
  
 Tipo de objeto: TestClasses.Order  
  
 Identificador de instancia de objeto: 448  
  
 PRUEBA DE EVALUACIÓN DE CONDICIÓN (COINCIDENCIA) 3/17/2004 10:31:17 AM  
  
 Identificador de la instancia de motor de reglas: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 Nombre de conjunto de reglas: orden  
  
 Expresión de prueba: TestClasses.Order.inventoryAvailable == True  
  
 Deja el valor del operando: null  
  
 Valor del operando de la derecha: True  
  
 Resultado de pruebas: False  
  
 ACTIVIDAD DE DATOS 3/17/2004 10:31:17 AM  
  
 Identificador de la instancia de motor de reglas: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 Nombre de conjunto de reglas: orden  
  
 Operación: Assert  
  
 Tipo de objeto: TestClasses.Shipment  
  
 Identificador de instancia de objeto: 447  
  
 ACTIVIDAD DE DATOS 3/17/2004 10:31:17 AM  
  
 Identificador de la instancia de motor de reglas: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 Nombre de conjunto de reglas: orden  
  
 Operación: Assert  
  
 Tipo de objeto: TestClasses.Inventory  
  
 Identificador de instancia de objeto: 446  
  
 PRUEBA DE EVALUACIÓN DE CONDICIÓN (COINCIDENCIA) 3/17/2004 10:31:17 AM  
  
 Identificador de la instancia de motor de reglas: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 Nombre de conjunto de reglas: orden  
  
 Expresión de prueba: TestClasses.Inventory.AllocateInventory == True  
  
 Deja el valor del operando: True  
  
 Valor del operando de la derecha: True  
  
 Resultado de pruebas: True  
  
 ACTUALIZACIÓN DE AGENDA 3/17/2004 10:31:17 AM  
  
 Identificador de la instancia de motor de reglas: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 Nombre de conjunto de reglas: orden  
  
 Operación: agregar  
  
 Nombre de regla: InventoryCheck  
  
 Criterios de resolución de conflictos: 0  
  
 REGLA ACTIVADA 3/17/2004 10:31:17 AM  
  
 Identificador de la instancia de motor de reglas: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 Nombre de conjunto de reglas: orden  
  
 Nombre de regla: InventoryCheck  
  
 Criterios de resolución de conflictos: 0  
  
 ACTIVIDAD DE DATOS 3/17/2004 10:31:17 AM  
  
 Identificador de la instancia de motor de reglas: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 Nombre de conjunto de reglas: orden  
  
 Operación: actualización  
  
 Tipo de objeto: TestClasses.Order  
  
 Identificador de instancia de objeto: 448  
  
 PRUEBA DE EVALUACIÓN DE CONDICIÓN (COINCIDENCIA) 3/17/2004 10:31:17 AM  
  
 Identificador de la instancia de motor de reglas: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 Nombre de conjunto de reglas: orden  
  
 Expresión de prueba: TestClasses.Order.inventoryAvailable == True  
  
 Deja el valor del operando: True  
  
 Valor del operando de la derecha: True  
  
 Resultado de pruebas: True  
  
 ACTUALIZACIÓN DE AGENDA 3/17/2004 10:31:17 AM  
  
 Identificador de la instancia de motor de reglas: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 Nombre de conjunto de reglas: orden  
  
 Operación: agregar  
  
 Nombre de regla: envío  
  
 Criterios de resolución de conflictos: 0  
  
 REGLA ACTIVADA 3/17/2004 10:31:17 AM  
  
 Identificador de la instancia de motor de reglas: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 Nombre de conjunto de reglas: orden  
  
 Nombre de regla: envío  
  
 Criterios de resolución de conflictos: 0  
  
 ACTIVIDAD DE DATOS 3/17/2004 10:31:17 AM  
  
 Identificador de la instancia de motor de reglas: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 Nombre de conjunto de reglas: orden  
  
 Operación: retirar  
  
 Tipo de objeto: TestClasses.Order  
  
 Identificador de instancia de objeto: 448  
  
 ACTIVIDAD DE DATOS 3/17/2004 10:31:17 AM  
  
 Identificador de la instancia de motor de reglas: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 Nombre de conjunto de reglas: orden  
  
 Operación: retirar  
  
 Tipo de objeto: TestClasses.Shipment  
  
 Identificador de instancia de objeto: 447  
  
 ACTIVIDAD DE DATOS 3/17/2004 10:31:17 AM  
  
 Identificador de la instancia de motor de reglas: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72  
  
 Nombre de conjunto de reglas: orden  
  
 Operación: retirar  
  
 Tipo de objeto: TestClasses.Inventory  
  
 Identificador de instancia de objeto: 446  
  
 En este ejemplo, la condición asociada a la regla Ship se evalúa como False la primera vez que se comprueba.  Sin embargo, cuando la regla InventoryCheck se activa, el campo inventoryAvailable de Order cambia y se emite un comando Actualizar en el motor para el objeto Order.  Esto hace que vuelva a evaluarse la regla Ship.  En esta ocasión la condición se evalúa como verdadera y la regla Ship se activa.  
  
> [!NOTE]
>  Si las reglas están escritas incorrectamente, el encadenamiento directo con la función Update puede ocasionar un bucle infinito.  Si esto ocurriera, recibirá un mensaje de error al probar la directiva en el Compositor de reglas de negocio con el texto "El motor de reglas detectó un bucle de ejecución".