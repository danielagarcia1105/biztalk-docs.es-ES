---
title: Configuración de Host Local generales (AS2) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 980daac2-8387-44cc-ae55-38639f759668
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de5e5c076e6b245e4a662f8132d027e927df6142
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233820"
---
# <a name="configuring-general-local-host-settings-as2"></a>Configuración de las opciones de host local generales (AS2)
Como parte de la configuración general del host local, puede especificar el tipo de contenido de los mensajes AS2 y si el nombre de archivo se conserva como parte del encabezado de mensaje AS2.  
  
> [!IMPORTANT]
>  Todas las propiedades se deshabilitan en esta página si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes de esta entidad** casilla de verificación al crear la entidad para la que se crea el contrato.  
>   
>  Las propiedades solo se deshabilitan en la ficha de acuerdo unidireccional que corresponde a las propiedades de los intercambios que se envían desde la entidad. Por ejemplo, si crea dos entidades, entidad A y entidad B y para la entidad A ha desactivado la casilla de verificación, la lista de propiedades anterior se deshabilita en el **entidad A -> B entidad** ficha de acuerdo unidireccional.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-the-general-settings"></a>Para configurar los parámetros generales  
  
1.  Crear un acuerdo de AS2 como se describe en [configurar las opciones generales (AS2)](../core/configuring-general-settings-as2.md). Para actualizar un acuerdo AS2 existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.  
  
2.  En una ficha de acuerdo unidireccional, bajo **configuración de Host Local** sección, haga clic en **General**.  
  
3.  Seleccione el **Comprobar lista de revocación de certificados antes de enviar el mensaje** casilla de verificación para determinar si el certificado que se usará en la firma de mensajes salientes se ha incluido en la lista de revocación de certificados, que indica se ha revocado dicho TI, o si se ha superado la fecha de expiración. Si es así, BizTalk Server no cifrará el mensaje sino que lo suspenderá. Si esta propiedad está desactivada, BizTalk Server no llevará a cabo esta comprobación.  
  
    > [!NOTE]
    >  Existe una latencia relacionada con la recuperación de la lista de revocaciones de certificados y con la búsqueda en ella.  
  
4.  Para **tipo de contenido predeterminado**, seleccione el tipo de contenido predeterminado que se debe utilizar la entidad para un mensaje AS2 saliente. Si el `ContentType` propiedad se establece en el contexto de una parte del cuerpo de mensaje, que configuración se usa para generar el mensaje saliente; en caso contrario, el valor de esta **tipo de contenido predeterminado** se utiliza la propiedad.  
  
5.  Seleccione el **transmitir el nombre de archivo en un encabezado MIME** casilla de verificación para enviar un nombre de archivo como parte del encabezado MIME para el mensaje AS2 saliente. Para especificar el nombre de archivo, seleccione **especificar nombre de archivo** o **tiene sistema generar nombre de archivo**.  
  
    > [!NOTE]
    >  Seleccionar **tiene sistema generar nombre de archivo** generará un nuevo valor GUID como el nombre de archivo de datos adjuntos enviados en el mensaje AS2.  
  
6.  Si seleccionó **especificar nombre de archivo**, escribir una propiedad de contexto o el valor de cadena en el **especificar nombre de archivo** campo. También puede habilitar **suspender mensaje si no encuentra la propiedad de contexto (%Property%))** para suspender el mensaje si la propiedad de contexto seleccionado no existe para el mensaje saliente.  
  
    > [!NOTE]
    >  Para especificar una propiedad de contexto, encierre el nombre de propiedad entre caracteres %. Por ejemplo, `%FILE.ReceivedFileName%`.  
  
7.  Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configuración del Host Local (AS2)](../core/configuring-local-host-settings-as2.md)