---
title: Traducir parámetros de consulta SAP en los comandos EXECQUERY de mySAP adaptador en BizTalk | Microsoft Docs
description: Guía para traducir consultas SAP para EXECQUERY, con ejemplos
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8a545e20-2607-4946-a60d-0a227b86d093
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8ffd480e952e0df7114a93f6cb2a5baf631ad96
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021699"
---
# <a name="translate-sap-query-parameters-into-execquery-command"></a>Traducir parámetros de consulta SAP en el comando EXECQUERY
Explica cómo se traducen los parámetros de una consulta en un texto de comando EXECQUERY. En este tema se usa el ejemplo de una consulta personalizada de SAP, ZQUERY_TST_NEW.  
  
## <a name="open-the-query-in-sap-gui"></a>Abra la consulta en la GUI de SAP  
 Realice los pasos siguientes para abrir la consulta en SAP. Los pasos que se proporcionan aquí son para consulta ZQUERY_TST_NEW y son específicos de las versiones de SAP.  
  
1. Ejecute la transacción SQ01.  
  
2. En el **consulta desde el grupo de usuarios** página, haga clic en **Quick Viewer**.  
  
3. En el **Quick Viewer** página, en el **vista rápida** cuadro de texto, escriba `ZQUERY_TST_NEW`y, a continuación, haga clic en **mostrar**.  
  
4. En el **Quick Viewer** página, haga clic en el **campos de selección** tab para enumerar todos los parámetros en la consulta.  
  
    La siguiente ilustración muestra todos los parámetros en la definición de consulta.  
  
    ![Lista de parámetros para una consulta SAP](../../adapters-and-accelerators/adapter-sap/media/sap-query-param-types.gif "sap_query_param_types")  
  
5. Haga clic en **Ejecutar**. Se muestra la página siguiente.  
  
    ![Proporcionar valores de parámetro para una consulta SAP](../../adapters-and-accelerators/adapter-sap/media/sap-query-all-params.gif "sap_query_all_params")  
  
6. Haga clic en las flechas de color amarillas para definir cada parámetro. Puede definir valores específicos de permitidos/no-permitido o puede definir un intervalo de valores permitido/no-permitido.  Debe especificarse la sintaxis EXECQUERY según los valores configurados en la GUI de SAP para cada parámetro.  
  
   La siguiente sección proporciona una explicación sobre cómo se definen los valores en la GUI de SAP y cómo esos valores se traducen a la sintaxis EXECQUERY.  
  
## <a name="frame-an-execquery-syntax"></a>Marco de una sintaxis EXECQUERY  
 Echemos un vistazo a lo que la sintaxis EXECQUERY aspecto según los valores de parámetro definidos en la definición de consulta. Para comprender esto, mostraremos algunos ejemplos de cómo configuran los valores para el primer parámetro, **número de dos dígitos**, se traducen en el **ZQUERY_TST_NEW** consulta.  
  
 En primer lugar, supongamos que los valores de la **único vals** ficha (con un punto verde) se definen como se muestra en la captura de pantalla siguiente:  
  
 ![Lista de valores de parámetro que una consulta puede tener](../../adapters-and-accelerators/adapter-sap/media/sap-query-param-val.gif "sap_query_param_val")  
  
> [!NOTE]
>  Este cuadro de diálogo aparece al hacer clic en la flecha amarilla en el **número de dos dígitos** parámetro.  
  
 En tal caso, la sintaxis EXECQUERY es similar:  
  
```  
EXECQUERY ZQUERY_TST_NEW @USERGROUP='mygroup', @P1 = '2', @P1 = '3', @P1 = '5'  
```  
  
 Para la misma consulta, además de los valores en el **único vals** ficha (con un punto verde), también puede tener los valores en el **único vals** ficha (con un punto rojo) se define como sigue:  
  
 ![Lista de valores de parámetro que no puede tener una consulta](../../adapters-and-accelerators/adapter-sap/media/2af88a57-4ff6-4bcc-8961-0f25dbfb8166.gif "2af88a57-4ff6-4bcc-8961-0f25dbfb8166")  
  
 En tal caso, la sintaxis de EXECQUERY es similar:  
  
```  
EXECQUERY ZQUERY_TST_NEW @USERGROUP='mygroup', @P1 = '2', @P1 = '3', @P1 = '5', NOT @P1 = '6', NOT @P1 = '8'  
```  
  
 Ahora, si agrega valores a la **intervalos** pestaña (con un punto verde), como se muestra en la captura de pantalla siguiente:  
  
 ![Intervalo de valores de parámetro que una consulta puede tener](../../adapters-and-accelerators/adapter-sap/media/74907c7d-5a7a-4a2d-a614-6a835eca1764.gif "74907c7d-5a7a-4a2d-a614-6a835eca1764")  
  
 la sintaxis EXECQUERY tiene el siguiente aspecto:  
  
```  
EXECQUERY ZQUERY_TST_NEW @USERGROUP='mygroup', @P1 = '2', @P1 = '3', @P1 = '5', NOT @P1 = '6', NOT @P1 = '8', @P1 BETWEEN '2' and '5'  
```  
  
 De forma similar, si agrega valores a la **intervalos** pestaña (con un punto rojo), como se muestra en la captura de pantalla siguiente:  
  
 ![Intervalo de valores de parámetro que no puede tener una consulta](../../adapters-and-accelerators/adapter-sap/media/ccc6a7bb-bc47-4325-8b58-094201f791bf.gif "ccc6a7bb-bc47-4325-8b58-094201f791bf")  
  
 la sintaxis EXECQUERY tiene el siguiente aspecto:  
  
```  
EXECQUERY ZQUERY_TST_NEW @USERGROUP='mygroup', @P1 = '2', @P1 = '3', @P1 = '5', NOT @P1 = '6', NOT @P1 = '8', @P1 BETWEEN '2' and '5', NOT @P1 BETWEEN '6' AND '8'  
```  
  
 Por simplicidad y la descripción, en este tema solo se habla el primer parámetro, **número de dos dígitos**. Puede usar métodos similares para determinar cómo se traducen los valores definidos para otros parámetros en una sintaxis EXECQUERY.  
  
