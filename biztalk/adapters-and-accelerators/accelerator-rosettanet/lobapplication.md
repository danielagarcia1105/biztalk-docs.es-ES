---
title: LOBApplication | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- trading partners, submitting actions
- LOBs, submitting actions
- LOBApplication utility
- trading partners, response messages
- LOBs, LOBApplication utility
- LOBs, response messages
ms.assetid: ad5986af-4175-49cd-806b-04e1fde63f55
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc9859e210036806cebcd76f63235d47ca972976
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978581"
---
# <a name="lobapplication"></a>LOBApplication
Use la utilidad LOBApplication para enviar un mensaje de acción o respuesta a un socio comercial, simulación de un programa de escritorio real de línea de negocio (LOB).  
  
 Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] proporciona mensajes de ejemplo en el \< *unidad*\>\Program Files (x86) \Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK\ Carpeta LOBApplication\SampleInstances.  
  
## <a name="location-in-sdk"></a>Ubicación en SDK  
 \<*unidad*\>\Program Files (x86) \Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK\LOBApplication  
  
## <a name="running-lobapplication"></a>Ejecutando LOBApplication  
  
#### <a name="to-run-lobapplication"></a>Para ejecutar LOBApplication  
  
1.  En el Explorador de Windows, desplácese a \< *unidad*\>\Program Files (x86) \Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK\\.  
  
2.  Haga doble clic en **LOBApplication.exe**, y, a continuación, presione ENTRAR.  
  
     Las páginas siguientes le solicitarán la información necesaria para ejecutar la utilidad.  
  
## <a name="syntax-for-lobapplication"></a>Sintaxis de LOBApplication  
 Use la **Proxy de aplicación de LOB** página para especificar nombres principal y socios, las propiedades del proceso de interfaz de socio (PIP) y las propiedades de mensaje para el mensaje enviado por la utilidad LOBApplication.  
  
 En la tabla siguiente se describe cómo usar cada campo en el **Proxy de aplicación de LOB** página.  
  
|Use|Para|  
|--------------|----------------|  
|**Nombre del perfil principal**|Escriba el nombre de la organización principal (entidad de origen).|  
|**Nombre del socio comercial**|Escriba el nombre del socio comercial (entidad de destino).|  
|**Nombre PIP**|Escriba el código para mostrar del PIP, por ejemplo, tipo **3A2**. Este valor distingue mayúsculas de minúsculas.|  
|**Versión PIP**|Escriba el número de versión del PIP, por ejemplo, tipo **V02.00**. Este valor distingue mayúsculas de minúsculas.|  
|**Id. de instancia PIP** (opcional)|Por ejemplo, escriba un identificador de instancia alfanumérico para el PIP, escriba **STD_3A2_V02.02**. Evite los caracteres especiales. El identificador debe ser único por código PIP y socios. Para los mensajes que están marcados como mensajes de acción, si el identificador de instancia está vacía, la utilidad de LOBApplication utiliza un valor HUID generado para el identificador de instancia de PIP. **Nota:** al seleccionar **respuesta** en el **mensaje categoría**, debe escribir el identificador de instancia PIP en este campo.|  
|**Nombre de archivo**|Haga clic en el botón de puntos suspensivos (...), vaya a la carpeta que contiene el archivo de instancia PIP y, a continuación, haga clic en el archivo de instancia PIP.|  
|**Categoría de mensaje**|Seleccione el tipo de mensaje (**acción** o **respuesta**).|  
|**Datos adjuntos**|Haga clic en **agregar**, vaya a la carpeta que contiene el archivo adjunto y, a continuación, haga clic en **abierto**.|  
|**Enviar mensaje**|Haga clic aquí para enviar el mensaje.|  
|**Estado**|Leer el estado de la acción en este campo.|  
  
## <a name="remarks"></a>Notas  
 La utilidad LOBApplication crea un mensaje con las propiedades especificadas y lo envía al socio comercial. Esta utilidad escribe los datos del servicio contenido en el mensaje en la base de datos BTARNDATA, en la tabla MessageFromLOB. Esta utilidad simula el envío de un mensaje de acción.  
  
 Los mensajes de ejemplo en la carpeta SampleInstances bajo la carpeta LOBApplication en el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK están preconfigurados para asumir los siguientes identificadores globales de negocio (GBIs): 123456789 para la organización principal y 987654321 para el socio comercial organización. Debe cambiar los mensajes de ejemplo en un editor de texto para usar otros GBIs.  
  
 Use la utilidad LOBApplication para simular un programa de escritorio de línea de negocio enviando un mensaje. Use la utilidad de LOBWebApplication para simular una aplicación Web de línea de negocio enviando un mensaje.  
  
## <a name="see-also"></a>Vea también  
 [Utilidades](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)   
 [LOBWebApplication](../../adapters-and-accelerators/accelerator-rosettanet/lobwebapplication.md)
