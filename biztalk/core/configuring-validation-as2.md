---
title: Configuración de la validación (AS2) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1ff22dc8-a544-46f9-86fb-f6845e2dfe46
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e135d048f7dede032803b5830faec4570fa1f4d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22234220"
---
# <a name="configuring-validation-as2"></a>Configuración de la validación (AS2)
En el acuerdo de socio comercial, debe especificar la configuración de validación para validar el mensaje AS2 entrante.  
  
> [!NOTE]
>  Ninguna propiedad se deshabilita en **entidad A -> B entidad** ficha de acuerdo unidireccional si se ha desactivado la **BizTalk Local procesa mensajes recibidos por la entidad o admite el envío de mensajes de esta entidad** casilla de verificación para la entidad A. Sin embargo, las propiedades siguientes están deshabilitadas en la misma página en la **parte B -> parte A** ficha si ha seleccionado la casilla de verificación al crear la entidad A.  
>   
>  -   **Usar la configuración de acuerdo para validación y MDN en lugar del encabezado de mensaje**  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-validation-properties"></a>Para configurar las propiedades de validación  
  
1.  Crear un acuerdo de AS2 como se describe en [configurar las opciones generales (AS2)](../core/configuring-general-settings-as2.md). Para actualizar un acuerdo AS2 existente, haga clic en el acuerdo en el **entidades y perfiles empresariales** página y haga clic en **propiedades**.  
  
2.  En una ficha de acuerdo unidireccional, haga clic en **validación**.  
  
3.  Seleccione el **usar la configuración de acuerdo para validación y MDN en lugar del encabezado de mensaje** casilla de verificación si desea que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] validar la firma digital, la compresión y el cifrado del mensaje entrante, en función de la configuración en el acuerdo. Si la casilla está desactivada, los mensajes se validarán contra las propiedades en el encabezado del mensaje AS2 en lugar de hacerlo en las propiedades del acuerdo para determinar este procesamiento. Para obtener una lista de encabezados de AS2, vea [mensajes AS2](../core/as2-messages.md).  
  
4.  Seleccione el **debe firmarse el mensaje** casilla de verificación para asegurarse de que el mensaje entrante está firmado.  
  
5.  Seleccione el **debe comprimirse el mensaje** casilla de verificación para asegurarse de que el mensaje entrante se comprime.  
  
6.  Seleccione el **debe cifrarse el mensaje** casilla de verificación para asegurarse de que el mensaje entrante está cifrado. Seleccione el algoritmo de cifrado de la **algoritmo de cifrado** lista desplegable. 

    **A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] y versiones más recientes**, compatibilidad con AES se incluye automáticamente. Las opciones incluyen DES3, RC2, AES128 (valor predeterminado), AES192 y AES256.
    
    Para anterior [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] versiones, las opciones son DES3 y RC2.
  
    > [!NOTE]
    >  Solo si se establece la propiedad adecuada, la canalización de recepción de AS2 comprueba la firma digital, descomprime el mensaje o descifra el mensaje. Si el **usar la configuración de acuerdo para validación y MDN en lugar del encabezado de mensaje** propiedad está seleccionada y el mensaje tiene propiedades de transporte diferentes para la firma, compresión y cifrado que las seleccionadas en el acuerdo propiedades y, a continuación, el descodificador AS2 suspenderá el mensaje y enviará un error.  
  
7.  Seleccione el **Comprobar lista de revocación de certificados** casilla de verificación para determinar si el certificado que se usará en la validación de un mensaje entrante se ha incluido en la lista de revocación de certificados, que indica que se ha revocado, o bien, si se ha superado la fecha de expiración. Si es así, BizTalk Server no descifrará el mensaje sino que lo suspenderá. Si esta propiedad está desactivada, BizTalk Server no llevará a cabo esta comprobación.  
  
    > [!NOTE]
    >  Existe una latencia relacionada con la recuperación de la lista de revocaciones de certificados y con la búsqueda en ella.  
  
8.  Seleccione el **comprobar mensajes duplicados dentro de** casilla de verificación para determinar si el mensaje entrante es un duplicado de mensajes recibidos anteriormente.  
  
     Si ha activado el **comprobar mensajes duplicados dentro de** establecer la propiedad, el **días** propiedad para indicar el intervalo de mensajes recibidos anteriormente que se usarán durante la comprobación de duplicados; Compruebe el **Suspender mensajes duplicados** propiedad para indicar que deben suspenderse los mensajes duplicados.  
  
    > [!NOTE]
    >  El **AS2-de** y **AS2-para** campos se usan para determinar si un mensaje es un duplicado. Si el mensaje contiene los mismos valores para estos campos que un mensaje recibido anteriormente, se marcará como duplicado aunque los demás encabezados o la carga sea diferente.  
  
9. Haga clic en **aplicar** para aceptar los cambios antes de continuar con la configuración o haga clic en **Aceptar** para validar los cambios y, a continuación, cierre el cuadro de diálogo.  
  
## <a name="see-also"></a>Vea también  
 [Configurar propiedades del acuerdo de AS2](../core/configuring-as2-agreement-properties.md)