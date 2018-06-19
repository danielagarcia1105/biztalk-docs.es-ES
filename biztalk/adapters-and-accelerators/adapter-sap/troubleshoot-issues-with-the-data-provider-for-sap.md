---
title: Solucionar problemas relacionados con el proveedor de datos para SAP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Data Provider for SAP, troubleshooting
- troubleshooting, Data Provider for SAP
ms.assetid: 6fe9baed-0404-4f15-b76e-88cc11c5ff46
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba61b75f95fad429c70da42479f22a32fa4e5a65
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217988"
---
# <a name="troubleshoot-issues-with-the-data-provider-for-sap"></a>Solucionar problemas relacionados con el proveedor de datos para SAP
Esta sección describe el uso de técnicas de solución de problemas para resolver errores de operaciones que pueden surgir al usar [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)].  
  
##  <a name="BKMK_SAPUnknownParam"></a>Error desconocido de parámetro mediante el proveedor de datos para SAP  
 **Problema**  
  
 El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] produce el siguiente error:  
  
```  
Microsoft.Data.SAPClient.SAPException: Failed to retrieve data from SAP server --- > Microsoft.ServiceModel.Channels.Common.XmlReaderParsingException: Unknown Parameter OUT_ZDATATABLE.  
```  
  
 **Causa**  
  
 La RFC personalizada, Z_EXTRACT_DATA_OO, instalado en el sistema SAP no es la versión más reciente. El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] usa una RFC personalizada, Z_EXTRACT_DATA_OO, para realizar las operaciones SELECT en la tabla SAP.  
  
 **Resolución**  
  
 Debe actualizar la solicitud de cambio personalizada a la última versión disponible. Esta RFC, Z_EXTRACT_DATA_OO, está disponible con la adapterpacknoversion. Para obtener más información acerca de cómo instalar y desinstalar la solicitud de cambio personalizada, vea [instalar RFC personalizado para el proveedor de datos para SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).
  
##  <a name="BKMK_SAPOOM"></a>Fuera de las excepciones de memoria al seleccionar los datos de una tabla SAP  
 **Problema**  
  
 El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] produce un excepción de memoria insuficiente al seleccionar los datos de un sistema SAP.  
  
 **Causa**  
  
 De forma predeterminada, la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] recupera 10.000 filas a la vez. Además, cada lote de filas recuperadas con el sistema SAP se almacena en la memoria. Por lo tanto,  
  
-   Si la tabla desde el que se está recuperando datos contiene un gran número de filas, o  
  
-   Si la tabla contiene columnas de tipos de datos que consumen una cantidad significativa de memoria,  
  
 El consumo de memoria por el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] aumenta considerablemente y puede provocar un excepción de memoria insuficiente.  
  
 **Resolución**  
  
 Puede cambiar el número máximo de filas recuperadas con el sistema SAP. Puede hacerlo mediante la especificación de una opción 'batchsize' con la instrucción SELECT. Por ejemplo:  
  
```  
SELECT * FROM <tablename> OPTION 'batchsize 1000'  
```  
  
 El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] ahora recupera solo 1000 filas a la vez y, por tanto, no lo consume gran cantidad de memoria.  
  
##  <a name="BKMK_SAPQueryExcep"></a>Excepción al ejecutar una consulta que toma parámetros con valores de fecha  
 **Problema**  
  
 Obtener la siguiente excepción al ejecutar una consulta mediante el comando EXECQUERY que tiene un parámetro que toma un valor de fecha:  
  
```  
ErrorCode=RFC_SYS_EXCEPTION. ErrorGroup=RFC_ERROR_SYSTEM_FAILURE.   
SapErrorMessage=Enter date in the format __.__.____.  
```  
  
 **Causa**  
  
 Al ejecutar las consultas que utilizan el comando EXECQUERY, siempre debe especificar valores de fecha en formato AAAAMMDD.  
  
 **Resolución**  
  
 Asegúrese de que especificar los valores de fecha en formato AAAAMMDD. Por ejemplo:  
  
```  
EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @P1='20080606'  
```  
  
##  <a name="BKMK_SAPNOVARIANT"></a>Excepción de NO_VARIANT ejecutar consultas con el comando EXECQUERY  
 **Problema**  
  
 Obtener la siguiente excepción al ejecutar una consulta mediante el comando EXECQUERY:  
  
```  
Exception: Details: ErrorCode=RFC_EXCEPTION. ErrorGroup=RFC_ERROR_APPLICATION_EXCEPTION. SapErrorMessage=NO_VARIANT.  
AdapterErrorMessage=Error returned by RfcCallReceiveEx while calling RFC: <RFC name>  
```  
  
 **Causa**  
  
 Puede haber dos causas probables para esta excepción:  
  
1.  La consulta que está intentando ejecutar tiene variantes definidas en el sistema SAP. Variantes hacen referencia a un conjunto de criterios de selección que puede especificar al ejecutar una consulta SAP almacenado. Por ejemplo, puede usar variantes para especificar valores predeterminados para las consultas.  
  
2.  La consulta que está intentando ejecutar ninguna de ellas tiene una variante definida ni espera un valor de parámetro que se pasan.  
  
 **Resolución**  
  
1.  Por motivo 1, asegúrese de que especificar el nombre de la variante asociado a la consulta. Por ejemplo:  
  
    ```  
    EXECQUERY ZTEST3 @USERGROUP='SYSTQV000024', @variant =  ‘variant1’  
    ```  
  
2.  Por motivo 2, asegúrese de que proporcionar un valor y el nombre del parámetro ficticio al especificar el comando de consulta. Por ejemplo, si "myquery" consulta no requiere ningún parámetro para ejecutar, el comando EXECQUERY debe especificarse como:  
  
    ```  
    EXECQUERY myquery @usergroup='mygroup',@P1 = 'dummy_value'  
    ```  
  
## <a name="see-also"></a>Vea también  
[Solucionar problemas del adaptador SAP](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)