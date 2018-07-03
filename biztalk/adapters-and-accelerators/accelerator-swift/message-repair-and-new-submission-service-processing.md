---
title: Reparación de mensajes y nuevo envío servicio procesamiento | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- repairing messages, MrsrRepair orchestration
- orchestrations, MrsrRepair orchestration
- InfoPath forms, valid forms
- messages, BAS
- unparsed messages
- repairing messages, unparsed messages
- messages, unparsed messages
- messages, InfoPath forms
- Business Rule Engine
- MrsrRepair orchestration
- InfoPath forms, messages
- BAS, messages
ms.assetid: fe2ee009-bf63-4bc0-b231-ad8a2633719f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8edec4b1c852a542068b1b5df6a8b58de390907f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004437"
---
# <a name="message-repair-and-new-submission-service-processing"></a>Reparación de mensajes y nuevo procesamiento de servicio de envío
La orquestación MrsrRepair controla todas las operaciones de reparación de mensajes y nuevo envío, incluido el procesamiento lo siguiente:  

-   Mensajes que necesita reparación  

-   Mensajes sin analizar  

-   Mensajes nuevos creados en el sitio MRSR  

## <a name="processing-messages-requiring-repair"></a>Procesamiento de mensajes que necesita reparación  
 Si un mensaje tiene que repararse, la orquestación recibe un aviso de que el mensaje entrante procede del desensamblador. Solo procesa los mensajes desde el Desensamblador si la funcionalidad de rol se establece para crear o reparación. La orquestación MrsrRepair se suscribe a mensajes en el cuadro de mensajes que tienen las siguientes propiedades:  

```  
A4SWIFT_Failed==true AND  
BTS_Operation=="A4SWIFT_DasmMarkedAsFailed" AND  
A4SWIFT_SwiftBound==true  
```  

 El puerto de entrada de la orquestación usada para la reparación de mensajes y nuevo envío está enlazado a la Sts.Outbox.Location de MrsrRepair la ubicación de recepción. El [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] programa se instala el programa de instalación esta ubicación de recepción predeterminado. Cuando se envían mensajes de los usuarios al sitio MRSR, recepción ubicación recoge los mensajes y los enruta a la orquestación MrsrRepair.  

 En la tabla siguiente se enumera válido [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formularios:  


| [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] Formularios |       |       |              |              |       |
|-------------------------------------------------------------------------------|-------|-------|--------------|--------------|-------|
|                                     MT010                                     | MT011 | MT012 |    MT015     |    MT019     | MT020 |
|                                     MT021                                     | MT022 | MT023 |    MT028     |    MT029     | MT030 |
|                                     MT031                                     | MT032 | MT035 |    MT036     |    MT037     | MT039 |
|                                     MT041                                     | MT042 | MT043 |    MT044     |    MT045     | MT046 |
|                                     MT047                                     | MT048 | MT049 |    MT050     |    MT051     | MT052 |
|                                     MT055                                     | MT056 | MT057 |    MT059     |    MT061     | MT062 |
|                                     MT063                                     | MT064 | MT065 |    MT066     |    MT067     | MT068 |
|                                     MT069                                     | MT072 | MT073 |    MT074     |    MT075     | MT076 |
|                                     MT077                                     | MT081 | MT082 |    MT083     |    MT085     | MT087 |
|                                     MT090                                     | MT092 | MT094 |    MT102     |  MT102PLUS   | MT103 |
|                                   MT103Plus                                   | MT104 | MT105 |    MT106     |    MT107     | MT110 |
|                                     MT111                                     | MT112 | MT121 |    MT190     |    MT191     | MT192 |
|                                     MT195                                     | MT196 | MT198 |    MT199     |    MT200     | MT201 |
|                                     MT202                                     | MT203 | MT204 |    MT205     |    MT206     | MT207 |
|                                     MT210                                     | MT256 | MT290 |    MT291     |    MT292     | MT295 |
|                                     MT296                                     | MT298 | MT299 |    MT300     |    MT303     | MT304 |
|                                     MT305                                     | MT306 | MT307 |    MT308     |    MT320     | MT321 |
|                                     MT330                                     | MT340 | MT341 |    MT350     |    MT360     | MT361 |
|                                     MT362                                     | MT364 | MT365 |    MT380     |    MT381     | MT390 |
|                                     MT391                                     | MT392 | MT395 |    MT396     |    MT398     | MT399 |
|                                     MT400                                     | MT405 | MT410 |    MT412     |    MT416     | MT420 |
|                                     MT422                                     | MT430 | MT450 |    MT4555    |    MT456     | MT490 |
|                                     MT491                                     | MT492 | MT495 |    MT496     |    MT498     | MT499 |
|                                     MT500                                     | MT501 | MT502 |    MT503     |    MT504     | MT505 |
|                                     MT506                                     | MT507 | MT508 |    MT509     |    MT510     | MT513 |
|                                     MT514                                     | MT515 | MT516 |    MT517     |    MT518     | MT519 |
|                                     MT524                                     | MT526 | MT527 |    MT528     |    MT529     | MT535 |
|                                     MT536                                     | MT537 | MT538 |    MT540     |    MT541     | MT542 |
|                                     MT543                                     | MT544 | MT545 |    MT546     |    MT547     | MT548 |
|                                     MT549                                     | MT558 | MT559 |    MT564     |    MT565     | MT566 |
|                                     MT567                                     | MT568 | MT569 | MT574_IRSLST | MT574_W8BENO | MT575 |
|                                     MT576                                     | MT577 | MT578 |    MT579     |    MT581     | MT582 |
|                                     MT584                                     | MT586 | MT587 |    MT588     |    MT589     | MT590 |
|                                     MT591                                     | MT592 | MT595 |    MT596     |    MT598     | MT599 |
|                                     MT600                                     | MT601 | MT604 |    MT605     |    MT606     | MT607 |
|                                     MT643                                     | MT644 | MT645 |    MT646     |    MT649     | MT690 |
|                                     MT691                                     | MT692 | MT695 |    MT696     |    MT698     | MT699 |
|                                     MT700                                     | MT701 | MT705 |    MT707     |    MT710     | MT711 |
|                                     MT720                                     | MT721 | MT730 |    MT732     |    MT734     | MT740 |
|                                     MT742                                     | MT747 | MT750 |    MT752     |    MT754     | MT756 |
|                                     MT760                                     | MT767 | MT768 |    MT769     |    MT790     | MT791 |
|                                     MT792                                     | MT795 | MT796 |    MT798     |    MT799     |       |
|                                     MT800                                     | MT801 | MT802 |    MT810     |    MT812     | MT813 |
|                                     MT820                                     | MT821 | MT822 |    MT823     |    MT824     | MT890 |
|                                     MT891                                     | MT892 | MT895 |    MT896     |    MT898     | MT899 |
|                                     MT900                                     | MT910 | MT920 |    MT935     |    MT940     | MT941 |
|                                     MT942                                     | MT950 | MT960 |    MT961     |    MT962     | MT963 |
|                                     MT964                                     | MT965 | MT966 |    MT967     |    MT970     | MT971 |
|                                     MT972                                     | MT973 | MT985 |    Mt986     |    MT990     | MT991 |
|                                     MT992                                     | MT995 | MT996 |    MT998     |    MT999     |       |

## <a name="processing-unparsed-messages"></a>Procesamiento de mensajes sin analizar  
 Si la orquestación MrsrRepair determina que no se pudo analizar un mensaje, Establece las marcas apropiadas y, a continuación, envía el mensaje a la MRSR sitio Bandeja de entrada para la reparación en el [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formulario para los mensajes sin analizar. Cuando la orquestación recibe el mensaje tras la reparación, Establece el BTS. Propiedad de operación a "[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_MRSRCompleted" y el [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed propiedad en False, y, a continuación, enruta el mensaje en el cuadro de mensajes. Estas propiedades Asegúrese de que el mensaje sin analizar reparado no escribe el proceso de reparación de mensajes nuevo.  

 Se llama a la forma de reparación sin analizar **mensaje sin analizar**.  

## <a name="processing-new-messages-created-in-mrsr"></a>Procesamiento de mensajes nuevos creados en MRSR  
 Si el mensaje recibido por la orquestación MrsrRepair se creó en el sitio MRSR, la orquestación recibe un aviso de que el mensaje entrante procede de [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] (no el desensamblador), y que se ha firmado el mensaje.  

## <a name="common-operations"></a>Operaciones comunes  
 La orquestación MrsrRepair realiza una serie de operaciones comunes en todos los mensajes, si necesita reparación, no se pudo analizar o son nuevos mensajes. La orquestación ejecuta un bucle que realiza las operaciones comunes en cada paso del flujo de trabajo, incluida la comprobación de regeneración de claves, crear, reparar y aprobar. Esta orquestación se usa independientemente de cuáles son los departamento y el rol.  

 Estos pasos comunes incluyen lo siguiente:  

1. Colocar el mensaje en un formulario de sobres.  

2. Enviar el mensaje al sitio MRSR.  

3. Recibir el mensaje (después de las acciones del usuario) de sitio MRSR a través de la Sts.Outbox.Location ubicación de recepción. Si se produce un tiempo de espera, la orquestación controla el tiempo de espera. Si se produce el tiempo de espera mientras un usuario está reparando, comprobar o aprobación de un mensaje, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] devuelve el mensaje a la Bandeja de entrada de reparación, restablecer el flujo de trabajo a la fase de reparación.  

   > [!NOTE]
   >  El puerto de entrada de la orquestación usada para la reparación de mensajes y nuevo envío está enlazado a la Sts.Outbox.Location de MrsrRepair la ubicación de recepción. Esta ubicación de recepción debe estar ejecutándose en un host de BizTalk que está enlazado a los servidores que tienen instalado el sitio de MRSR. Ese host normalmente es BizTalkServerApplication, pero puede ser un host diferente. Si es un host diferente, debe comprobar que los servidores al que está enlazado el host tengan instalado el sitio de MRSR.  

4. Compruebe que la firma escrita por el usuario es adecuada para el rol y almacenar esa firma para comprobar las restricciones de funciones.  

5. Si el contenido del mensaje se almacena en un paso anterior, comparar el contenido recibido desde el sitio MRSR con el mensaje almacenado. La orquestación produce un error en el mensaje si no hay una coincidencia.  

6. Si el usuario rechazó los cambios, producirá un error en el mensaje.  

7. Realizar validación XSD y BRE en el mensaje si el usuario ha aceptado los cambios.  

8. Si procede, ir al paso siguiente.  

## <a name="customizing-the-repair-orchestration"></a>Personalización de la orquestación de reparación  
 Puede personalizar la orquestación MrsrRepair mediante la adición de funcionalidad de procesamiento previo o posterior al procesamiento. Por ejemplo, podría agregar una orquestación a los pasos de preprocesamiento, o agregar una forma de orquestación antes de la forma de envío existente para promocionar una propiedad. Sin embargo, no puede crear o modificar los acuerdos o perfiles asociados con la reparación de mensajes y nuevo envío, porque la orquestación MrsrRepair no sería consciente de ellos. No se puede agregar nuevas definiciones de rol más allá de aprobador, Comprobador, creador o taller de reparación. También no se puede cambiar la estructura, o agregar funcionalidad al núcleo de la orquestación.  

## <a name="business-rules-policies"></a>Las directivas de reglas de negocios  
 Para el proceso de reparación, la orquestación de reparación llama el motor de reglas de negocios (BRE) de BizTalk para cargar la directiva principal para el tipo de mensaje, por ejemplo, MT103_Master_Policy.xml. La orquestación pasa el BRE el tipo de mensaje y el cuerpo. La directiva principal del mensaje contiene una lista de todas las demás directivas que pertenecen a ese tipo de mensaje. El BRE carga todas las directivas para el tipo de mensaje. Estas directivas incluyen SWIFT_Reference_Policy, SWIFT_PartyIdentifier_Policy, directivas de reglas de red y la directiva de validación específica del tipo de mensaje. El BRE ejecuta todas las directivas que se muestran en la directiva principal, independientemente de los errores y devuelve todos los errores.