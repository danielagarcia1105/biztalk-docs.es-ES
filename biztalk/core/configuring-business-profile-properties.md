---
title: Configuración de propiedades de perfil de negocio | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.admin.businessprofile.properties
ms.assetid: d3c87777-9bcd-4482-bbb7-efea08cdeead
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b43f6af9999b0c09698d6cebe6fbe9af505a42a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-business-profile-properties"></a>Configuración de propiedades de perfil de negocio
Un perfil de negocio representa una división de negocio de una organización. Al igual que una organización puede tener muchas divisiones (contabilidad, compras, envíos, etc.), una entidad puede tener muchos perfiles de negocio, cada uno de los cuales representa una división de negocio de una organización. Las propiedades del perfil de negocio contienen la información siguiente:  
  
-   Información general como el nombre del perfil de negocio  
  
-   Identidades únicas que pueden asociarse a un perfil de negocio  
  
-   Los valores de codificación (para mensajes X12 y EDIFACT) y los valores de protocolo (AS2) que definen el modo en que un perfil de negocio puede enviar o recibir mensajes de otra entidad.  
  
 Para obtener más información acerca de los perfiles de negocio, consulte [perfiles de negocio](http://msdn.microsoft.com/library/f8286130-57fe-40ed-9fd8-81da2c8baaaf). Para obtener más información sobre la configuración de protocolo de codificación y transporte, consulte [configuración del protocolo](../core/protocol-settings.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-business-profile-properties"></a>Para configurar propiedades de perfiles de negocio  
  
1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **partes** nodo. En el **entidades y perfiles empresariales** panel, haga clic en una entidad, seleccione Nuevo y, a continuación, haga clic en **perfil de negocio**.  
  
2.  En el **General** ficha la **General** página, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Escriba un nombre de perfil de negocio.|  
    |**Description**|Escriba una descripción para el perfil de negocio.|  
    |**Propiedades adicionales: nombre / valor**|Escriba un par nombre-valor para almacenar cualquier información sobre la entidad. Puede agregar tantos pares nombre-valor como desee. **Nota:** el servidor BizTalk Server no usa los pares de nombre-valor para ningún proceso; estos datos son solo para fines informativos.|  
    |**Eliminar**|Haga clic aquí para eliminar el par nombre-valor seleccionado.|  
  
3.  Si es necesario, agregue las identidades de negocio para los perfiles de negocio. En el **General** ficha la **identidades** página, realice lo siguiente:  
  
    > [!NOTE]
    >  La adición de identidades de negocio en esta fase no es obligatoria. Puede agregar las identidades de negocio más tarde también, como parte de un acuerdo para el perfil de negocio. Si elige agregar identidades de negocio ahora, estarán disponibles al crear un acuerdo para este perfil de negocio.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Nombre**|Haga clic en la celda vacía y desde la cuadrícula desplegable, seleccione un cuerpo de autenticación que proporcione identidades de negocio únicas a las organizaciones. Por ejemplo, **D-U-N-S (Dun & Bradstreet)**. Dos socios de negocio pueden optar por una identidad de negocio acordada entre ambos. Para estos escenarios, seleccione **definidos mutuamente** (para EDIFACT) o **definidos mutuamente (X12)** (para X12).|  
    |**Qualifier**|Muestra un valor predefinido basado en el valor seleccionado para **nombre**.|  
    |**Valor**|Escriba un valor para la identidad de negocio. Debe tener en cuenta las siguientes consideraciones al proporcionar un valor para las identidades de negocio.<br /><br /> -Para una entidad determinada, puede tener más de un perfil de negocio mediante la misma combinación de nombre de la identidad y el valor de identidad. Por ejemplo, puede tener dos perfiles de negocio para una entidad con **nombre** como **definidos mutuamente (X12)** y **valor** como **THEM**.<br />-Entre entidades, no puede tener dos perfiles de negocio con la misma combinación de nombre de la identidad y el valor de identidad.|  
    |**Eliminar**|Haga clic para eliminar la identidad seleccionada.|  
  
4.  Si es necesario, agregue la configuración de protocolo para mensajes codificados en X12.  
  
    1.  En el **propiedades de perfil** cuadro de diálogo, en la esquina superior derecha, haga clic en **Agregar configuración de protocolo**, seleccione **configuración de codificación**y, a continuación, haga clic en **X12** .  
  
    2.  Se agrega una nueva pestaña de junto a la **General** ficha.  En el **común** página de recién agregado ficha la **nombre de configuración de protocolo** texto cuadro, escriba un nombre para identificar este conjunto de opciones de protocolo de codificación. El nombre de la ficha también se establece en el valor que especifique en el cuadro de texto.  
  
    3.  Se pueden definir propiedades X12 como parte de un perfil de negocio o directamente en el acuerdo. Si define las propiedades como parte del perfil de negocio, la misma configuración estará disponible cuando cree un acuerdo. Puesto que se pueden establecer las mismas propiedades en dos ubicaciones, este documento proporciona instrucciones de cómo establecer las propiedades únicamente como parte del acuerdo. Si desea establecer las propiedades como parte del perfil de negocio, la tabla de abajo proporciona vínculos con las secciones pertinentes que contienen información sobre el establecimiento de propiedades.  
  
        > [!NOTE]
        >  La configuración de entrada se aplica a todos los mensajes recibidos por una entidad. La configuración de salida se aplica a todos los mensajes enviados por una entidad.  
  
        > [!NOTE]
        >  Aunque especifique la configuración de protocolo como parte del perfil de negocio, siempre puede sobrescribir la configuración para un acuerdo específico.  
  
        |Configuración|Descripción disponible en|  
        |-------------|------------------------------|  
        |**Configuración de la entrada > configuración de intercambio > validación**|[Configuración de la validación (configuración de intercambio de X12)](../core/configuring-validation-x12-interchange-settings.md)|  
        |**Configuración de la entrada > configuración de intercambio > configuración de Host Local**|[Configuración del Host Local (configuración de intercambio de X12)](../core/configuring-local-host-settings-x12-interchange-settings.md) (configuración del receptor)|  
        |**Configuración de la entrada > configuración del conjunto de transacciones > lista del conjunto de transacciones**|[Configurar conjunto de transacciones lista (X12)](../core/configuring-transaction-set-list-x12.md)|  
        |**Configuración de la entrada > configuración del conjunto de transacciones > validación**|[Configuración de la validación (configuración de conjunto de transacciones de X12)](../core/configuring-validation-x12-transaction-set-settings.md)|  
        |**Configuración de la entrada > configuración del conjunto de transacciones > configuración de Host Local**|[Configuración del Host Local (configuración de conjunto de transacciones de X12)](../core/configuring-local-host-settings-x12-transaction-set-settings.md)|  
        |**La configuración de salida > configuración de intercambio > identificadores adicionales**|[Configuración de identificadores (X12)](../core/configuring-identifiers-x12.md)|  
        |**La configuración de salida > configuración de intercambio > confirmaciones**|[Configuración de confirmaciones (X12)](../core/configuring-acknowledgements-x12.md)|  
        |**La configuración de salida > configuración de intercambio > sobres**|[Configuración de sobres (configuración de intercambio de X12)](../core/configuring-envelopes-x12-interchange-settings.md)|  
        |**La configuración de salida > configuración de intercambio > juegos de caracteres y separadores**|[Configuración de juego de caracteres y separadores (X12)](../core/configuring-charset-and-separators-x12.md)|  
        |**La configuración de salida > configuración de intercambio > números de Control**|[Configuración del Host Local (configuración de intercambio de X12)](../core/configuring-local-host-settings-x12-interchange-settings.md) (configuración del remitente)|  
        |**La configuración de salida > configuración del conjunto de transacciones > sobres**|[Configuración de sobres (configuración de conjunto de transacciones de X12)](../core/configuring-envelopes-x12-transaction-set-settings.md)|  
  
        > [!NOTE]
        >  Se puede tener más de una configuración de protocolo de codificación X12 definida para un perfil de negocio.  
  
5.  Si es necesario, agregue la configuración de protocolo para mensajes codificados en EDIFACT.  
  
    1.  En el **propiedades de perfil** cuadro de diálogo, en la esquina superior derecha, haga clic en **Agregar configuración de protocolo**, seleccione **configuración de codificación**y, a continuación, haga clic en  **EDIFACT**.  
  
    2.  Se agrega una nueva pestaña de junto a la **General** ficha.  En el **común** página de recién agregado ficha la **nombre de configuración de protocolo** texto cuadro, escriba un nombre para identificar este conjunto de opciones de protocolo de codificación. El nombre de la ficha también se establece en el valor que especifique en el cuadro de texto.  
  
    3.  Se pueden definir propiedades EDIFACT como parte de un perfil de negocio o directamente en el acuerdo. Si define las propiedades como parte del perfil de negocio, la misma configuración estará disponible cuando cree un acuerdo. Puesto que se pueden establecer las mismas propiedades en dos ubicaciones, este documento proporciona instrucciones de cómo establecer las propiedades únicamente como parte del acuerdo. Si desea establecer las propiedades como parte del perfil de negocio, la tabla de abajo proporciona vínculos con las secciones pertinentes que contienen información sobre el establecimiento de propiedades.  
  
        > [!NOTE]
        >  La configuración de entrada se aplica a todos los mensajes recibidos por una entidad. La configuración de salida se aplica a todos los mensajes enviados por una entidad.  
  
        > [!NOTE]
        >  Aunque especifique la configuración de protocolo como parte del perfil de negocio, siempre puede sobrescribir la configuración para un acuerdo específico.  
  
        |Configuración|Descripción disponible en|  
        |-------------|------------------------------|  
        |**Configuración de la entrada > configuración de intercambio > identificadores adicionales**|[Configuración de identificadores (EDIFACT).](../core/configuring-identifiers-edifact.md)|  
        |**Configuración de la entrada > configuración de intercambio > validación**|[Configuración de la validación (configuración de intercambio EDIFACT)](../core/configuring-validation-edifact-interchange-settings.md)|  
        |**Configuración de la entrada > configuración de intercambio > configuración de Host Local**|[Configuración del Host Local (configuración de intercambio EDIFACT)](../core/configuring-local-host-settings-edifact-interchange-settings.md) (configuración del receptor)|  
        |**Configuración de la entrada > configuración del conjunto de transacciones > lista del conjunto de transacciones**|[Configurar conjunto de transacciones lista (EDIFACT).](../core/configuring-transaction-set-list-edifact.md)|  
        |**Configuración de la entrada > configuración del conjunto de transacciones > validación**|[Configuración de la validación (configuración del conjunto de transacciones EDIFACT)](../core/configuring-validation-edifact-transaction-set-settings.md)|  
        |**Configuración de la entrada > configuración del conjunto de transacciones > configuración de Host Local**|[Configuración del Host Local (configuración del conjunto de transacciones EDIFACT)](../core/configuring-local-host-settings-edifact-transaction-set-settings.md)|  
        |**La configuración de salida > configuración de intercambio > identificadores adicionales**|[Configuración de identificadores (EDIFACT).](../core/configuring-identifiers-edifact.md)|  
        |**La configuración de salida > configuración de intercambio > confirmaciones**|[Configuración de confirmaciones (EDIFACT).](../core/configuring-acknowledgements-edifact.md)|  
        |**La configuración de salida > configuración de intercambio > sobres**|[Configuración de sobres (configuración de intercambio EDIFACT)](../core/configuring-envelopes-edifact-interchange-settings.md)|  
        |**La configuración de salida > configuración de intercambio > juegos de caracteres y separadores**|[Configuración de juego de caracteres y separadores (EDIFACT).](../core/configuring-charset-and-separators-edifact.md)|  
        |**La configuración de salida > configuración de intercambio > números de Control**|[Configuración del Host Local (configuración de intercambio EDIFACT)](../core/configuring-local-host-settings-edifact-interchange-settings.md) (configuración del remitente)|  
        |**La configuración de salida > configuración del conjunto de transacciones > sobres**|[Configuración de sobres (configuración del conjunto de transacciones EDIFACT)](../core/configuring-envelopes-edifact-transaction-set-settings.md)|  
  
        > [!NOTE]
        >  Se puede tener más de una configuración de protocolo de codificación EDIFACT definida para un perfil de negocio.  
  
6.  Si es necesario, agregue la configuración de protocolo para el transporte AS2.  
  
    1.  En el **propiedades de perfil** cuadro de diálogo, en la esquina superior derecha, haga clic en **Agregar configuración de protocolo**, seleccione **configuración de transporte**y, a continuación, haga clic en **AS2** .  
  
    2.  Se agrega una nueva pestaña de junto a la **General** ficha.  En el **común** página de recién agregado ficha la **nombre de configuración de protocolo** texto cuadro, escriba un nombre para identificar este conjunto de configuración del protocolo de transporte. El nombre de la ficha también se establece en el valor que especifique en el cuadro de texto.  
  
    3.  Se pueden definir propiedades AS2 como parte de un perfil de negocio o directamente en el acuerdo. Si define las propiedades como parte del perfil de negocio, la misma configuración estará disponible cuando cree un acuerdo. Puesto que se pueden establecer las mismas propiedades en dos ubicaciones, este documento proporciona instrucciones de cómo establecer las propiedades únicamente como parte del acuerdo. Si desea establecer las propiedades como parte del perfil de negocio, la tabla de abajo proporciona vínculos con las secciones pertinentes que contienen información sobre el establecimiento de propiedades.  
  
        > [!NOTE]
        >  La configuración de entrada se aplica a todos los mensajes recibidos por una entidad. La configuración de salida se aplica a todos los mensajes enviados por una entidad.  
  
        > [!NOTE]
        >  Aunque especifique la configuración de protocolo como parte del perfil de negocio, siempre puede sobrescribir la configuración para un acuerdo específico.  
  
        |Configuración|Descripción disponible en|  
        |-------------|------------------------------|  
        |**Configuración de la entrada > validación**|[Configuración de la validación (AS2)](../core/configuring-validation-as2.md)|  
        |**Configuración de la entrada > configuración de Host Local > configuración de HTTP para mensajes**|[Configuración de HTTP para mensajes](../core/configuring-http-settings-for-messages.md)|  
        |**Configuración de la entrada > configuración de Host Local > genera la configuración de MDN**|[Configuración de MDN de receptor](../core/configuring-receiver-mdn-settings.md)|  
        |**Configuración de la entrada > configuración de Host Local > mensaje de seguimiento (NRR)**|[Configuración de mensajes de receptor (NRR) de seguimiento](../core/configuring-receiver-message-tracking-nrr.md)|  
        |**La configuración de salida > confirmaciones (MDN)**|[Configuración de confirmaciones (MDN) (AS2)](../core/configuring-acknowledgements-mdns-as2.md)|  
        |**La configuración de salida > configuración de Host Local > General**|[Configuración de Host Local generales (AS2)](../core/configuring-general-local-host-settings-as2.md)|  
        |**La configuración de salida > configuración de Host Local > configuración de HTTP para MDN**|[Configuración de HTTP para MDN](../core/configuring-http-settings-for-mdns.md)|  
        |**La configuración de salida > configuración de Host Local > mensaje de seguimiento (NRR)**|[Configuración de mensajes de remitente (NRR) de seguimiento](../core/configuring-sender-message-tracking-nrr.md)|  
        |**La configuración de salida > el certificado de firma**|[Configuración de certificados de firma (AS2)](../core/configuring-signature-certificates-as2.md)|  
  
        > [!NOTE]
        >  Se puede tener más de una configuración de protocolo de codificación AS2 definida para un perfil de negocio.  
  
7.  Haga clic en **aplicar** para aceptar las propiedades o haga clic en **Aceptar** para completar la configuración. Cualquier acción validará la configuración.  
  
## <a name="see-also"></a>Vea también  
 [Configurar propiedades de EDI](../core/configuring-edi-properties.md)