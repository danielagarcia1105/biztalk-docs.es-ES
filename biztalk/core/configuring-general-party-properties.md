---
title: Configuración de propiedades de entidad General | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bbabf7e5-6388-4900-ad47-cf5d5af396b5
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7af5cea62d3f0ce51109d7aec8d06eb6b0abb1bd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967933"
---
# <a name="configuring-general-party-properties"></a>Configuración de las propiedades generales de la entidad
Una entidad o socio comercial representa una organización participante en una relación de negocios. Las propiedades de la entidad contienen la información siguiente:  

- Información general como el nombre de la entidad  

- Puertos de envío asociados a la entidad  

- Certificados asociados a la entidad  

  Para obtener más información sobre las entidades o socios comerciales, vea [socios comerciales](../core/trading-partners-and-business-profiles.md).  

## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  

### <a name="to-configure-party-properties"></a>Para configurar propiedades de entidades  

1. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **partes**, apunte a **New**y, a continuación, haga clic en **entidad**.  

2. En el **General** página de la **las propiedades de entidad** diálogo cuadro, realice lo siguiente:  


   |                                                Use                                                 |                                                                                                                                                                                                                                                                      Para                                                                                                                                                                                                                                                                       |
   |---------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |                                                **Nombre**                                                 |                                                                                                                                                                                                                                                                  Escribir un nombre de entidad.                                                                                                                                                                                                                                                                  |
   | **BizTalk local procesa mensajes recibidos por la entidad o admite el envío de mensajes desde esta entidad** | Active esta casilla para especificar que la entidad representa el mismo socio comercial que también hospeda [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. **Importante:** para que dos entidades TPM solución que usa las canalizaciones de cuadro se incluye con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], debe seleccionar esta casilla para al menos una entidad. **Nota:** si desactiva esta casilla de verificación, algunas propiedades se deshabilitarán mientras cree los acuerdos para esta entidad. |
   |                                **Propiedades adicionales: nombre / valor**                                 |                                                                                                                                                Escriba un par nombre-valor para almacenar cualquier información sobre la entidad. Puede agregar tantos pares nombre-valor como desee. **Nota:** el servidor BizTalk Server no usa los pares de nombre-valor para cualquier procesamiento; estos datos son solo para fines informativos.                                                                                                                                                 |
   |                                               **Eliminar**                                                |                                                                                                                                                                                                                                                     Haga clic aquí para eliminar el par nombre-valor seleccionado.                                                                                                                                                                                                                                                     |


3. En el **puertos de envío** página de la **las propiedades de entidad** diálogo cuadro, realice lo siguiente.  

   > [!NOTE]
   >  En BizTalk Server, la asociación de puertos de envío se realiza en el nivel de acuerdo. El **puertos de envío** disponible como parte de las propiedades de entidad es para mantener la compatibilidad de la página. Siempre que asocie un puerto de envío con un acuerdo, la configuración del puerto de envío se propaga a la configuración de la entidad y también se puede ver la asociación de puerto de envío en esta página. Sin embargo, el proceso inverso no es verdadero. No se puede asociar un puerto de envío con una entidad y, después, hacer que ese puerto de envío esté automáticamente disponible como parte de la configuración del acuerdo. Para obtener más información sobre cómo asociar puertos de envío con un acuerdo, vea [configuración de asociación de envío del puerto (X12)](../core/configuring-send-port-association-x12.md) o [configuración de asociación de puerto de envío (EDIFACT)](../core/configuring-send-port-association-edifact.md).  

   |       Use        |                                      Para                                      |
   |-----------------------|--------------------------------------------------------------------------------------|
   | **Puertos de envío - nombre** |          Seleccionar en la lista desplegable un puerto de envío para enlazarlo con la entidad.          |
   | **Puertos de envío - URI**  |                           Ver la dirección del puerto de envío.                            |
   |      **Quitar**       |                Quitar de la entidad el puerto de envío seleccionado.                |
   |    **Propiedades**     | Haga clic para mostrar el **propiedades de puerto de envío** cuadro de diálogo para el puerto de envío seleccionado. |


4. En el **certificado** página, realice lo siguiente:  


   |        Use        |                                                                                                                                                 Para                                                                                                                                                 |
   |------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |       **Examinar**       |                                                 Haga clic para mostrar el **Seleccionar certificado** cuadro de diálogo, donde podrá seleccionar el certificado de firma desde el almacén de certificados equipo Local u otras personas a aplicar a los mensajes transmitidos a la entidad.                                                 |
   |    **Nombre común**     |                                                                                                                            Ver una descripción del certificado seleccionado.                                                                                                                             |
   |     **Huella digital**     | Ver la huella digital del certificado de clave privada utilizado para la resolución de la entidad y la comprobación de la firma. La huella digital del certificado tiene el formato HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH, donde H es un dígito hexadecimal (un número entre 0 y 9) o una letra de la a F. |
   | **Quitar certificado** |                                                                                                                                 Quitar el certificado que aparece en pantalla.                                                                                                                                 |


5. Haga clic en **aplicar** para aceptar las propiedades o haga clic en **Aceptar** para completar la opción de configuración. Cualquier acción validará la configuración.  

## <a name="see-also"></a>Vea también  
 [Configuración de las propiedades de EDI](../core/configuring-edi-properties.md)