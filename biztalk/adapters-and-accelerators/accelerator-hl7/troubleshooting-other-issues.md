---
title: Otros problemas de solución de problemas | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting
ms.assetid: 1f115f64-45ce-445d-ab18-092f4a6a232c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2753d85050506d5b8ca05ca3b3438bb767a26322
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009501"
---
# <a name="troubleshooting-other-issues"></a>Solucionar otros problemas
Direcciones de otros problemas relacionados con Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)].  
  
## <a name="message-rejected-by-the-btahl7-engine"></a>Mensajes rechazados por el motor de BTAHL7  
  
### <a name="symptom"></a>Síntoma  
 Los mensajes se rechazan aleatoriamente por el motor de mensajería.  
  
**Causa posible** : según el estándar HL7, enumeración los valores de tabla 0338 contiene el valor "L & me". 6 de campo del segmento PRA puede contener este valor. Puesto que [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] el carácter "&" se trata como un delimitador, se rechaza el mensaje.  
  
**Resolución** : existen tres posibles soluciones para resolver este problema:  
  
1.  En la instancia de mensaje, controlar el carácter "&" a través de una secuencia de escape, como el uso de la combinación de caracteres L\T\I.  
  
2.  Agregar un valor de enumeración de "LI" en PRA 6 en el esquema y use este valor en su lugar en la instancia de mensaje.  
  
3.  Utilizar un separador de subcomponente completamente diferente en MSH2; Sin embargo, esta solución concreto puede no resultar práctica de función de su entorno.  
  
## <a name="cannot-edit-the-hl7-schema-using-visual-studio"></a>No se puede editar el esquema HL7 con Visual Studio  
  
### <a name="symptom"></a>Síntoma  
 No se puede editar el esquema de HL7 mediante Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].  
  
**Causa posible** : [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] no admite algunos esquemas de HL7.  
  
**Resolución** : Use otros editores, como Microsoft Notepad, para editar esquemas de HL7.  
  
## <a name="message-handling-fails-with-no-errors-logged"></a>Se produce un error en el control de mensajes sin errores registrados  
  
### <a name="symptom"></a>Síntoma  
 El sistema procesa los mensajes sin registrar los mensajes de error o colocar los mensajes en la cola de mensajes suspendidos.  
  
**Causa posible** : el **HeaderSpecType** y **DocumentSpecType** los valores de propiedad distinguen mayúsculas de minúsculas. Al implementar las canalizaciones, un error tipográfico en estos nombres pueden que los mensajes se maneja y colocar sin errores registrados.  
  
**Resolución** : Observe a minúsculas cuando se usa el **HeaderSpecType** y **DocumentSpecType** los nombres de valor de propiedad.  
  
## <a name="message-header-fields-are-not-validated-correctly"></a>Campos de encabezado de mensaje no se ha validado correctamente  
  
### <a name="symptom"></a>Síntoma  
 Error al validar un campo de encabezado.  
  
 Motivo: El [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] serializador valida una propiedad promocionada, no la propiedad de contexto de campo de encabezado real.  
  
**Causa posible** : se ha producido un cambio a la propiedad promocionada correspondiente al encabezado a través de una orquestación o un mapa.  
  
**Resolución** : las propiedades de contexto de encabezados de mensaje MSH1 MSH2 y MSH5{1-3} deben actualizarse para que estén en la sincronización con los datos.  
  
## <a name="the-mllp-adapter-is-not-removed-during-uninstall"></a>No se quita el adaptador MLLP durante la desinstalación  
  
### <a name="symptom"></a>Síntoma  
 El programa de instalación de BTAHL7 no quitó el adaptador MLLP durante la desinstalación de BTAHL7.  
  
**Causa posible** : se ha producido un puerto de envío o ubicación de recepción con un tipo de transporte de MLLP. El programa de instalación de BTAHL7 no puede quitar el adaptador MLLP si es que se hace referencia en cualquiera de los proyectos de BizTalk Server.  
  
**Resolución** : una vez completada la desinstalación de BTAHL7, realice lo siguiente:  
  
1.  En la consola de administración de BizTalk Server, quite todas las ubicaciones de recepción y puertos de envío que tienen un tipo de transporte de MLLP, o cambiar el tipo de transporte de las ubicaciones de recepción o puertos de envío a otro tipo.  
  
2.  En la consola de administración, elimine el adaptador de MLLP.  
  
3.  Reinicie la instancia de host.  
  
## <a name="btahl7-cannot-be-uninstalled-if-biztalk-server-has-already-been-uninstalled"></a>No se puede desinstalar BTAHL7 si ya se ha desinstalado el servidor BizTalk Server  
  
### <a name="symptom"></a>Síntoma  
 Desinstalar [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)] da como resultado el siguiente error:  
  
`A network error while attempting to read from file C:\Windows\Installer\Microsoft BizTalk <version\> Accelerator for HL7.msi`
  
**Causa posible** : [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] se desinstaló antes de la desinstalación de [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)] se ha intentado. Debe desinstalar [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)] antes de desinstalar [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)].  
  
**Resolución** : reinstalar [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)], a continuación, desinstale [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]y, a continuación, desinstale [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="messages-are-still-sent-after-the-applicable-mllp-send-port-has-been-stopped"></a>Todavía se envían los mensajes una vez detenido el puerto de envío MLLP aplicable  
  
### <a name="symptom"></a>Síntoma  
 Después de detener un MLLP puerto de envío, los mensajes que se envían a través de ese puerto de envío no detiene, pero seguirán enviándose.  
  
**Causa posible** : cuando se detiene un puerto de envío, la conexión permanece establecida hasta que se quita al detener el host de BizTalk. Como resultado, los mensajes se siguen enviando una vez detenido el puerto de envío. Esto ocurre porque Biztalk Server no llama a en el adaptador MLLP durante el inicio o detención del puerto de envío. BizTalk Server llama al adaptador de MLLP solo durante el inicio y detención del servicio de host.  
  
**Resolución** : puede quitar la conexión y detener transmisión de mensajes, detenga la instancia de host es el controlador de envío para el puerto de envío que ha detenido. Sin embargo, la detención de dicha instancia de host puede afectar a otros mensajes que no desea detener. Si sabe que este es el caso, debe configurar el puerto de envío de forma diferente al crearla. Debe crear otra instancia de host para que actúe como controlador de envío sólo este puerto de envío MLLP (o un subconjunto de los puertos de envío). A continuación, puede detener transmisión de mensajes desde este puerto de envío deteniendo esta instancia de host. Esto, a continuación, no afectará a la transmisión de mensajes en otros puertos de envío que usan otros controladores de envío.  
  
## <a name="see-also"></a>Vea también  
 [Solución de problemas y problemas conocidos en HL7](../../adapters-and-accelerators/accelerator-hl7/troubleshooting-and-known-issues-in-hl7.md)