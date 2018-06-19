---
title: Seguridad con el adaptador SAP y BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- credentials, protecting
- Enterprise Single Sign-On
- security, when using BizTalk Server
- security, protecting credentials
- SSO
ms.assetid: 702cd0f9-d8e1-4dad-8774-b552481d5390
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4689424deced097d901464263d75e5ae10e4b99f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217780"
---
# <a name="security-with-the-sap-adapter-and-biztalk-server"></a>Seguridad con el adaptador SAP y BizTalk Server
Al configurar un puerto de envío o un puerto de recepción (ubicación) mediante el uso de la administración de BizTalk Server de la consola o utilizar el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para recuperar esquemas de mensaje para una solución de BizTalk, debe proporcionar credenciales para el sistema SAP. Es importante proporcionar estas credenciales de una manera segura para ayudar a evitar que se revelen a actores potencialmente malintencionados. Este tema describe cómo proporcionar una forma más segura de credenciales para el [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] para soluciones de BizTalk Server.  
  
 Una descripción más general de seguridad en el contexto de las soluciones de BizTalk es un tema amplio y queda fuera del ámbito de esta documentación. Para obtener información acerca de cómo hacer que las soluciones de BizTalk más segura, consulte la [seguro y proteger los mensajes de BizTalk](../../core/secure-and-protect-your-biztalk-messages.md).  
  
## <a name="how-do-i-protect-credentials-when-i-use-the-consume-adapter-service-biztalk-project-add-in"></a>¿Cómo proteger las credenciales cuando utilizo el Consume Adapter Service complemento del proyecto de BizTalk?  
 Cuando se usa el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para recuperar esquemas de mensaje para una solución de BizTalk, debe proporcionar un nombre de usuario y una contraseña para el sistema SAP. Debe hacerlo desde el **seguridad** pestaña en el **configurar el adaptador** cuadro de diálogo. Esto garantiza que las credenciales no se mostrarán en el **Uri** campo de la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] cuadro de diálogo, donde cualquier persona con acceso a la pantalla del equipo puede leer. Para obtener más información acerca de cómo recuperar esquemas de mensaje mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], incluida la forma de especificar un nombre de usuario y una contraseña para el sistema SAP, consulte [obtener metadatos para operaciones de SAP en Visual Studio](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md).  
  
## <a name="how-do-i-protect-credentials-when-i-configure-a-send-port-or-a-receive-location"></a>¿Cómo se puede proteger las credenciales cuando configura un puerto de envío o una ubicación de recepción?  
 Las soluciones de BizTalk usan el adaptador personalizado de WCF de Microsoft BizTalk para consumir servicios WCF. El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] es un enlace personalizado de WCF que permite a los clientes usar el sistema SAP como si fuera un servicio WCF. Soluciones de BizTalk consumen la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] a través de puertos de envío y ubicaciones de recepción que están configurados para usar el adaptador de WCF-Custom, que a su vez, está, configurado para usar el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] como su transporte. Para obtener más información acerca de cómo configurar puertos de envío y puertos de recepción (ubicaciones de recepción), incluido cómo configurar el adaptador WCF-Custom, vea [configurar manualmente un enlace de puerto físico para el adaptador SAP](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md).  
  
 Configurar las credenciales del sistema SAP el **credenciales** pestaña de la **propiedades de transporte de WCF-Custom** cuadro de diálogo para puertos de envío o de la **otros** pestaña de la  **Propiedades de transporte de WCF-Custom** cuadro de diálogo para las ubicaciones de recepción. Dado que el adaptador WCF-Custom admite inicio de sesión único (SSO) empresarial, puede proporcionar un nombre de usuario y contraseña o una aplicación afiliada SSO en cualquiera de estas pestañas. Los temas siguientes describen ambas opciones.  
  
### <a name="user-name-password-credentials"></a>Credenciales de contraseña de nombre de usuario  
 Solo se deben proporcionar un nombre de usuario y una contraseña de la **credenciales** ficha (para los puertos de envío) o la **otros** ficha (para ubicaciones de recepción) en la **propiedades de transporte de WCF-Custom**cuadro de diálogo. Esto garantiza lo siguiente:  
  
-   Las credenciales no se mostrará en el **Uri** campo del cuadro de diálogo. Esto evita que aquellos que tienen acceso a la pantalla (o que tienen permisos que puedan ver el puerto de envío o propiedades de la ubicación de recepción) vean sus credenciales.  
  
-   La contraseña no se escribirán en el archivo de enlace si exporta el puerto de envío o recepción de enlace de puerto. Esto evita que cualquiera con acceso al archivo de ver la contraseña.  
  
### <a name="enterprise-single-sign-on-and-sso-affiliate-applications"></a>Aplicaciones afiliadas de SSO y Enterprise Single Sign-On  
 Puede configurar el adaptador de WCF-Custom para usar SSO para obtener las credenciales para el sistema SAP. SSO utiliza una base de datos y un secreto principal para cifrar y almacenar las credenciales de usuario. También proporciona servicios para asignar cuentas de Microsoft Windows a credenciales secundarias que se utilizan para tener acceso a un sistema back-end. Mediante el uso de SSO, puede asignar una cuenta de Windows a un nombre de usuario y una contraseña en el sistema SAP.  
  
 SSO utiliza *aplicaciones afiliadas* y *asignaciones de SSO* para asignar las credenciales para el sistema back-end. Una aplicación afiliada es una entidad lógica de SSO que hace referencia a un sistema o una aplicación que requiera credenciales secundarias. Una asignación de SSO está asociada a una aplicación afiliada. Se asigna una cuenta de Windows a las credenciales secundarias usadas esa cuenta para tener acceso al sistema afiliado o la aplicación. Una asignación de SSO puede asociarse con una cuenta de usuario de Windows o con un grupo.  
  
 Usar SSO con el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], debe hacer lo siguiente.  
  
1.  Crear una aplicación afiliada de SSO para contener el usuario las credenciales de contraseña de nombre para el sistema SAP. A menudo, este paso se realiza por una persona con tipos especiales de privilegios de administrador de SSO.  
  
2.  Crear un usuario o la asignación de grupos de la aplicación afiliada que se asigna la cuenta de Windows para el nombre de usuario y una contraseña que se utilizan para establecer una conexión con el sistema SAP. Dependiendo de la instalación, un usuario podría ser capaz de realizar este paso o puede requerir una persona con tipos especiales de privilegios de administrador de SSO.  
  
> [!NOTE]
>  Cuando se configura para SSO, el adaptador WCF-Custom utiliza servicios proporcionados por SSO para obtener el nombre de usuario SAP y la contraseña de la base de datos SSO. Proporciona estas (sin cifrar) a la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], de modo que el adaptador puede abrir una conexión con el sistema SAP. SSO no proporciona ningún cifrado o la protección a través de la conexión entre el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] y el sistema SAP.  
  
 Para obtener información sobre cómo usar SSO, incluida la información sobre cómo crear aplicaciones afiliadas y asignaciones SSO, vea [mediante SSO](../../core/using-sso.md). Para obtener más información acerca de SSO, vea [implementar Enterprise Single Sign-On](../../core/implementing-enterprise-single-sign-on.md).  
  
## <a name="the-acceptcredentialsinuri-binding-property"></a>La propiedad de enlace AcceptCredentialsInUri  
 El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] superficies la **AcceptCredentialsInUri** propiedad de enlace. Esta propiedad determina si se permiten las credenciales del sistema SAP en el URI de conexión. De forma predeterminada, **AcceptCredentialsInUri** es **false** y [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] produce una excepción si las credenciales se incluyen en el URI.  
  
 Esta propiedad aparece porque hay determinados escenarios de programación que se requieren las credenciales estén presentes en el URI de conexión. Nunca debe ser el caso cuando se está configurando un puerto de envío o una ubicación de recepción, o cuando se usa el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para recuperar los esquemas de mensaje desde el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]. En tales casos, se recomienda no establecer **AcceptCredentialsInUri** a **true**. Para obtener más información sobre la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] propiedades de enlace, consulte [obtener información sobre el adaptador de BizTalk para propiedades de enlace de ORacle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).  
  
 El **AcceptCredentialsInUri** no está disponible en la propiedad de enlace [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] en el **enlace** ficha al configurar un WCF-Custom o WCF-SAP de recepción o puerto de envío. Para establecer el valor de la **AcceptCredentialsInUri** propiedad de enlace, debe abrir el archivo de enlaces de adaptador (archivo XML) que se crea después de haber generado los metadatos que utilizan el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]y, a continuación, busque esta propiedad de enlace en el archivo. Especifique un valor adecuado para esta propiedad de enlace, guarde el archivo de enlace y, a continuación, importe el archivo de enlace en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Vea [enlaces del adaptador SAP reutilizar](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md) para obtener instrucciones.  
  
## <a name="see-also"></a>Vea también  
[Prácticas recomendadas para proteger el adaptador SAP](../../adapters-and-accelerators/adapter-sap/best-practices-to-secure-the-sap-adapter.md)  
 [Proteger las aplicaciones de SAP](../../adapters-and-accelerators/adapter-sap/secure-your-sap-applications.md)   