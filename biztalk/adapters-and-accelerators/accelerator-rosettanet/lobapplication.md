---
title: LOBApplication | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- trading partners, submitting actions
- LOBs, submitting actions
- LOBApplication utility
- trading partners, response messages
- LOBs, LOBApplication utility
- LOBs, response messages
ms.assetid: ad5986af-4175-49cd-806b-04e1fde63f55
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af11e69c90c9d211e36e706710c1d1de44a72399
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="lobapplication"></a>LOBApplication
Use la utilidad LOBApplication para enviar un mensaje de acción o respuesta a un socio comercial, simulando un programa de escritorio real de línea de negocio (LOB).  
  
 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] incluye ejemplos de mensajes en el \< *unidad*\>\Program BizTalk \<versión\> Acelerador para RosettaNet\SDK\LOBApplication\ Carpeta SampleInstances.  
  
## <a name="location-in-sdk"></a>Ubicación en SDK  
 \<*unidad*\>\Program BizTalk \<versión\> Acelerador para RosettaNet\SDK\LOBApplication  
  
## <a name="running-lobapplication"></a>Ejecutando LOBApplication  
  
#### <a name="to-run-lobapplication"></a>Para ejecutar LOBApplication  
  
1.  En el Explorador de Windows, desplácese a \< *unidad*\>\Program BizTalk \<versión\> Acelerador para RosettaNet\SDK\\.  
  
2.  Haga doble clic en **LOBApplication.exe**, y, a continuación, presione ENTRAR.  
  
     Las páginas siguientes le solicitan ingresar la información necesaria para ejecutar la utilidad.  
  
## <a name="syntax-for-lobapplication"></a>Sintaxis de LOBApplication  
 Use la **Proxy de aplicación de LOB** página para especificar propiedades de mensaje para el mensaje enviado por la utilidad LOBApplication, propiedades del proceso de interfaz de socio (PIP) y nombres de inicio y de los asociados.  
  
 En la tabla siguiente describe cómo usar cada campo en el **Proxy de aplicación de LOB** página.  
  
|Use|Para|  
|--------------|----------------|  
|**Nombre del perfil de inicio**|Escriba el nombre de la organización principal (entidad de origen).|  
|**Nombre del socio comercial**|Escriba el nombre del socio comercial (entidad de destino).|  
|**Nombre del PIP**|Escriba el código para mostrar del PIP, por ejemplo, tipo **3A2**. Este valor distingue mayúsculas de minúsculas.|  
|**Versión PIP**|Escriba el número de versión del PIP, por ejemplo, tipo **V02.00**. Este valor distingue mayúsculas de minúsculas.|  
|**Id. de instancia PIP** (opcional)|Por ejemplo, escriba un identificador de instancia alfanumérico para el PIP, escriba **STD_3A2_V02.02**. Evite los caracteres especiales. El identificador debe ser único por socio comercial y por código PIP. Para los mensajes que están marcados como mensajes de acción, si el identificador de instancia está vacío, la utilidad LOBApplication utiliza el valor HUID generado para el identificador de instancia de PIP. **Nota:** cuando selecciona **respuesta** en el **categoría del mensaje**, debe escribir el identificador de instancia PIP en este campo.|  
|**Nombre de archivo**|Haga clic en el botón de puntos suspensivos (...), vaya a la carpeta que contiene el archivo de instancia PIP y, a continuación, haga clic en el archivo de instancia PIP.|  
|**Categoría de mensaje**|Seleccione el tipo de mensaje (**acción** o **respuesta**).|  
|**Datos adjuntos**|Haga clic en **agregar**, desplácese a la carpeta que contiene el archivo de datos adjuntos y, a continuación, haga clic en **abiertos**.|  
|**Enviar mensaje**|Haga clic aquí para enviar el mensaje.|  
|**Estado**|Leer el estado de la acción en este campo.|  
  
## <a name="remarks"></a>Comentarios  
 La utilidad LOBApplication crea un mensaje con las propiedades especificadas y lo envía al socio comercial. Esta utilidad escribe los datos de contenido del servicio en el mensaje en la base de datos BTARNDATA, en la tabla MessageFromLOB. Esta utilidad simula el envío de un mensaje de acción.  
  
 Los mensajes de ejemplo en la carpeta SampleInstances en la carpeta LOBApplication en la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK están preconfigurados para supone los siguientes identificadores globales de negocio (GBIs): 123456789 para la organización principal y 987654321 para el socio comercial organización. Debe cambiar los mensajes de ejemplo en un editor de texto para usar otros GBIs.  
  
 Use la utilidad LOBApplication para simular un programa de escritorio de línea de negocio enviando un mensaje. Use la utilidad LOBWebApplication para simular una aplicación Web de línea de negocio enviando un mensaje.  
  
## <a name="see-also"></a>Vea también  
 [Utilidades](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)   
 [LOBWebApplication](../../adapters-and-accelerators/accelerator-rosettanet/lobwebapplication.md)