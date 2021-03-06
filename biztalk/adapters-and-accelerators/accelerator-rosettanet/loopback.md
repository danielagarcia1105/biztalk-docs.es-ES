---
title: Bucle invertido | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- agreements, 0A1 agreements
- loopbacks, running
- loopbacks, 0A1 agreements
- loopbacks, about loopbacks
- loopbacks, 0A1 messages
- agreements, loopback agreements
- messages, 0A1 messages
- loopbacks
- Loopback utility
- loopbacks, syntax
- 0A1 messages
- loopbacks, Loopback utility
- syntax [loopbacks]
- agreements, Loopback utility
ms.assetid: b4ebbdac-05be-4dfc-a133-6b752994e85a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 656441fe65e840302928e90ea22e21327fee33cd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978053"
---
# <a name="loopback"></a>Loopback
Use la utilidad de bucle invertido para generar automáticamente un acuerdo de bucle invertido que es una copia reflejada de un acuerdo de principal a asociado. Esto le permite realizar intercambios de mensajes de principal a asociado y de asociado a principal en un único equipo. Puede usar esta utilidad para un escenario con 0A1 mensajes o un escenario sin mensajes 0A1. Puede crear un acuerdo de bucle invertido para un contrato de mensaje de acción (que no sean de 0A1) o un contrato 0A1.  

 También puede usar la utilidad para dar de alta o de baja de la organización principal para un rol de remitente. Cuando usa la utilidad para habilitar la organización principal, crea dos puertos de envío, \<principal\>. Async y \<inicio\>. Sincronización, que la organización usa para comunicarse con su asociado.  

## <a name="location-in-sdk"></a>Ubicación en SDK  
 \<*unidad*\>\ archivos de programa (x86) \Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK\  

## <a name="running-loopback"></a>Ejecución de bucle invertido  

#### <a name="to-run-loopback"></a>Para ejecutar el bucle invertido  

1.  Abra un símbolo del sistema.  

2.  Mover a \< *unidad*\>\ archivos de programa (x86) \Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK\\.  

3.  En el símbolo del sistema, escriba **bucle invertido**, escriba los conmutadores requeridos y correspondientes y, a continuación, presione ENTRAR.  

## <a name="syntax-for-loopback"></a>Sintaxis de bucle invertido  
 A continuación se muestra la sintaxis que se utiliza para iniciar esta utilidad de línea de comandos:  

```  
Loopback [/enable|/disable <home_organization>] [/mirror|/unmirror <agreement_name>] [/NoF <0A1_agreement>]  
```  

## <a name="syntax-description"></a>Descripción de la sintaxis  
 En la tabla siguiente describe cada parte de la sintaxis que usa la utilidad de bucle invertido.  

|**Sintaxis**|**Descripción**|  
|----------------|---------------------|  
|**habilitar**|Da de alta la organización designada en < home_organization > para un rol de remitente. Crea dos puertos de envío, \<inicio\>. Async y \<inicio\>. Sincronización, que el socio que se utiliza para comunicarse con la organización principal.|  
|**disable**|Da de baja la organización principal para un rol de remitente.|  
|**home_organization**|El asociado que se va a dar de alta o dado de baja para un rol de remitente.|  
|**reflejado**|Crea un acuerdo de bucle invertido según el acuerdo designado en \< **agreement_name**\>.|  
|**se realizaron**|Elimina el acuerdo de bucle invertido basándose en el acuerdo designado en \< **agreement_name\>**.|  
|**agreement_name**|El acuerdo para reflejar ni se realizaron en el escenario de bucle invertido.|  
|**Ndel**|Establece el **0A1 acuerdo** propiedad del contrato de mensaje de acción reflejado por la utilidad de bucle invertido para \<0A1_agreement\>. Un **/nde** conmutador solo puede agregarse a un comando de bucle invertido que también contiene un **/mirror** cambie.|  
|**0A1_agreement**|Un contrato 0A1 se utilizan en el acuerdo reflejado de agreement_name. Este contrato se genera mediante un contrato de servicio de respuesta 0A1 la creación de reflejo.|  

## <a name="remarks"></a>Notas  
 La utilidad de bucle invertido cambia los roles en la creación del acuerdo de bucle invertido. Si una organización se encontraba la organización principal en el contrato original, la utilidad facilita la organización del asociado en el acuerdo de bucle invertido. De forma similar, si una organización se encontraba la organización del asociado en el contrato original, la utilidad facilita la organización principal en el acuerdo de bucle invertido. La utilidad también cambia la configuración de la propiedad de rol principal. Si la propiedad de rol principal era el iniciador en el contrato original, la utilidad facilita el servicio de respuesta y viceversa. Todas las demás propiedades son iguales.  

 La utilidad de bucle invertido nombra el acuerdo de bucle invertido con el mismo nombre que el contrato original, precedido de "bucle invertido:". Para evitar confusiones, no asigne a un acuerdo a partir de "bucle invertido".  

 Si ejecuta la utilidad en un contrato para el que ya haya generado un acuerdo de bucle invertido, la utilidad unmirrors el acuerdo de bucle invertido existente y crea un nuevo contrato de bucle invertido.  

 Necesita la utilidad de bucle invertido porque no se puede crear un acuerdo reflejado en el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] consola de administración. No se puede crear un acuerdo en el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console para la que se invierten la organización principal y organización del asociado de propiedades de la función principal y todos los demás campos son idénticos a los campos de un acuerdo existente. De forma similar, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] no admite el cambio en el acuerdo de bucle invertido directamente en la consola. Recibirá un error si intenta abrir un acuerdo de bucle invertido en la consola. Si tiene que realizar ningún cambio en el acuerdo de bucle invertido, cambie el contrato original y, a continuación, ejecute la utilidad de bucle invertido en nuevo para volver a generar el acuerdo de bucle invertido.  

> [!IMPORTANT]
>  El escenario de bucle invertido no es compatible con los acuerdos firmados. En este escenario, un mensaje firmado se producirá un error de validación, porque [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] le permite configurar una entidad única con un certificado de firma. La organización principal y una organización asociada no pueden usar el mismo certificado de firma. Esta es una limitación en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] relacionados con la identificación de forma exclusiva una entidad mediante el uso de un certificado de firma. Por lo tanto, no hay dos partes de BizTalk pueden compartir el mismo certificado.  

 Para obtener más información sobre la implementación de bucle invertido, consulte [Tutorial de bucle invertido](../../adapters-and-accelerators/accelerator-rosettanet/loopback-tutorial.md).  

## <a name="using-loopback-with-0a1-agreements"></a>Uso de bucle invertido con acuerdos 0A1  
 Puede configurar un escenario de bucle invertido para generar mensajes de 0A1 (notificación de error). Para ello, debe crear los siguientes contratos de la organización propia: un contrato de mensaje de acción de solicitud, un acuerdo de 0A1 iniciador y un contrato de servicio de respuesta 0A1. A continuación, debe ejecutar la utilidad de bucle invertido en cada uno de estos acuerdos para crear los siguientes acuerdos para la organización del asociado: un contrato de mensaje de acción de respuesta, un acuerdo de 0A1 iniciador y un contrato de servicio de respuesta 0A1. Esto es necesario porque no puede usar el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] consola de administración para crear estos acuerdos.  

 El conjunto completo de los acuerdos de debe incluir los contratos para los siguientes mensajes. Modo de ilustración, el mensaje de acción es un 3A4:  

-   Un contrato de Home_to_Partner_3A4 (mensaje de acción). Un acuerdo para iniciar el mensaje de acción PIP de la organización principal a la organización del asociado.  

-   Contrato Home_to_Partner_Initiator_0A1. Un acuerdo para iniciar un 0A1 PIP de la organización principal a la organización del asociado.  

-   Contrato Home_to_Partner_Responder_0A1. Un acuerdo para recibir un 0A1 PIP de la organización del asociado a la organización principal.  

-   Contrato Loopback:Home_to_Partner_3A4 (mensaje de respuesta). Un acuerdo para recibir un 3A4 PIP de la organización principal a la organización del asociado.  

-   Contrato Loopback:Home_to_Partner_Responder_0A1. Un acuerdo para iniciar un 0A1 PIP de la organización asociada a la organización principal.  

-   Loopback:Home_to_Partner_Initiator_0A1. Un acuerdo para recibir un 0A1 PIP de la organización principal a la organización del asociado.  

## <a name="creating-the-loopback-agreements-for-0a1-messages"></a>Cree los acuerdos de bucle invertido para mensajes 0A1  
 Para crear el conjunto completo de contratos, debe usar la utilidad de bucle invertido para crear los contratos de mensaje de acción y 0A1 en el asociado. Las siguientes tablas muestran las operaciones de bucle invertido necesarias para generar al asociado de contratos de bucle invertido. Modo de ilustración, en este tema se usa un mensaje de 3A4 en las tablas.  

|Paso|Acuerdos de inicio|  
|----------|---------------------|  
|1, 4|Home_to_Partner_3A4<br /><br /> Organización de inicio: inicio<br /><br /> Organización de asociado: asociado<br /><br /> Rol organizativo de inicio: iniciador<br /><br /> Acuerdo de 0A1: Home_to_Partner_Initiator_0A1<br /><br /> Descripción: De acuerdo para iniciar 3A4 PIP desde casa al asociado|  
|2|Home_to_Partner_Initiator_0A1<br /><br /> Inicio: inicio<br /><br /> Partner: asociado<br /><br /> Rol: iniciador<br /><br /> Descripción: De acuerdo para iniciar el PIP 0A1 desde casa al asociado|  
|3|Home_to_Partner_Responder_0A1<br /><br /> Inicio: inicio<br /><br /> Partner: asociado<br /><br /> Rol: servicio de respuesta<br /><br /> Descripción: Contrato para recibir PIP 0A1 de asociado a la página principal|  

|Paso|Acuerdos de socios (reflejado mediante Loopback.exe)|  
|----------|--------------------------------------------------------|  
|7|Loopback:Home_to_Partner_3A4<br /><br /> Inicio: asociado<br /><br /> Partner: inicio<br /><br /> Rol: servicio de respuesta<br /><br /> Acuerdo de 0A1: Loopback:Home_to_Partner_Responder_0A1<br /><br /> Descripción: Contrato para recibir 3A4 PIP desde casa al asociado<br /><br /> Bucle invertido comando Create: /mirror Home_to_Partner_3A4 NoF Loopback:Home_to_Partner_Responder_0A1 de bucle invertido|  
|5|Loopback:Home_to_Partner_Responder_0A1<br /><br /> Inicio: asociado<br /><br /> Partner: inicio<br /><br /> Rol: iniciador<br /><br /> Descripción: De acuerdo para iniciar el PIP 0A1 de asociado a la página principal<br /><br /> Bucle invertido comando Create: /mirror Home_to_Partner_Responder_0A1 de bucle invertido|  
|6|Loopback:Home_to_Partner_Initiator_0A1<br /><br /> Inicio: asociado<br /><br /> Partner: inicio<br /><br /> Rol: servicio de respuesta<br /><br /> Descripción: Contrato para recibir PIP 0A1 desde casa al asociado<br /><br /> Bucle invertido comando Create: /mirror Home_to_Partner_Initiator_0A1 de bucle invertido|  

 Ejecute los comandos de bucle invertido en estas tablas como parte del procedimiento siguiente.  

#### <a name="to-create-the-agreements-for-a-loopback-scenario-using-0a1-messages"></a>Para crear los contratos para un escenario de bucle invertido mediante mensajes 0A1  

1. En el [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] consola de administración, cree un acuerdo para el mensaje de acción de solicitud que se enviarán por la organización principal.  

2. Crear un acuerdo para el mensaje de 0A1 de iniciador que se enviarán por la organización principal y realice lo siguiente:  


   |         Use         |                  Para                  |
   |--------------------------|----------------------------------------------|
   |   **Mi organización**    |        Se establece en la organización principal.         |
   | **Organización del asociado** |             Establezca al socio comercial.              |
   |      **Rol principal**       | Establecido en **PIP error notificador (iniciador)**. |


3. Uso de [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] consola de administración, crear un acuerdo para el mensaje de respuesta 0A1 para enviarse a la organización principal y realice lo siguiente:  


   |         Use         |                      Para                      |
   |--------------------------|------------------------------------------------------|
   |   **Mi organización**    |            Se establece en la organización principal.             |
   | **Organización del asociado** |                 Establezca al socio comercial.                  |
   |      **Rol principal**       | Establecido en **Administrador de informes de error (respondedor)**. |


4. Uso de [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] set de la consola de administración, el **0A1 acuerdo** propiedad para el contrato de mensaje de acción del solicitud de la organización principal para el nombre del contrato de 0A1 iniciador de la organización principal.  

5. Con la utilidad de bucle invertido, cree un acuerdo para el mensaje de 0A1 de iniciador que se enviarán por la organización del asociado. Para ello, el servicio de respuesta de creación de reflejo 0A1 contrato para la organización principal. Esto crea un nuevo contrato 0A1 con el nombre **bucle invertido:\<nombre del contrato 0A1\>**. El `My organization` propiedad está establecida en el socio comercial, el `Partner organization` propiedad está establecida en la organización principal y el `Home role` propiedad es **PIP error notificador (iniciador)**.  

6. Con la utilidad de bucle invertido, cree un acuerdo para el mensaje de respuesta 0A1 para la organización del asociado. Para ello el acuerdo de iniciador 0A1 para la organización principal de la creación de reflejo. Esto crea un nuevo contrato 0A1 con el nombre **bucle invertido:\<nombre del contrato 0A1\>**. El `My organization` propiedad está establecida en el socio comercial, el `Partner organization` propiedad está establecida en la organización principal y el `Home role` propiedad es **Administrador de informes de error (respondedor)**.  

7. Con la utilidad de bucle invertido, cree un acuerdo para el mensaje de acción de respuesta para la organización del asociado. En el mismo comando, debe establecer la propiedad de acuerdo 0A1 el contrato de servicio de respuesta 0A1 para el socio comercial. Para ello, el contrato de mensaje de acción de solicitud de la organización propia de creación de reflejo y el uso de la **/nde** cambie con el nombre del acuerdo de 0A1 de servicio de respuesta del asociado. Esto crea un nuevo contrato de mensaje de acción de respuesta con el nombre **bucle invertido:\<nombre del contrato\>**. El `My organization` propiedad está establecida en el asociado y se establece la propiedad 0A1 de acuerdo al acuerdo de 0A1 de servicio de respuesta del asociado.  

## <a name="see-also"></a>Vea también  
 [Utilidades](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)   
 [Tutorial de bucles invertidos](../../adapters-and-accelerators/accelerator-rosettanet/loopback-tutorial.md)
