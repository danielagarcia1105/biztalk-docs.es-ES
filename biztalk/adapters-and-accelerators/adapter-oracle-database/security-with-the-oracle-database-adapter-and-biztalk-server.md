---
title: Seguridad con el adaptador de la base de datos de Oracle y el servidor de BizTalk | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- user name password credentials
- SSO mapping
- credentials
- credentials, protecting
- credentials, security considerations
- affiliate application
ms.assetid: c7e0be64-4ab9-4ee3-b88a-4f8f5f07b280
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47c4ad584f23b156d2f28397952074d358995136
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="security-with-the-oracle-database-adapter-and-biztalk-server"></a>Seguridad con el adaptador de la base de datos de Oracle y el servidor BizTalk Server
Al configurar un puerto de envío o un puerto de recepción (ubicación) mediante el uso de la administración de BizTalk Server de la consola o utilizar el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para recuperar esquemas de mensaje para una solución de BizTalk, debe proporcionar credenciales para la base de datos de Oracle. Es importante proporcionar estas credenciales de una manera segura para ayudar a evitar que se revelen a actores potencialmente malintencionados. Este tema describe cómo proporcionar una forma más segura de credenciales para el [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] para soluciones de BizTalk Server.  
  
 Una descripción más general de seguridad en el contexto de las soluciones de BizTalk es un tema amplio y queda fuera del ámbito de esta documentación. Para obtener información acerca de cómo hacer que las soluciones de BizTalk más segura, consulte [seguro y proteger los mensajes de BizTalk](../../core/secure-and-protect-your-biztalk-messages.md).  
  
## <a name="how-do-i-protect-credentials-when-i-use-the-consume-adapter-service-biztalk-project-add-in-or-add-adapter-metadata-wizard"></a>¿Cómo proteger las credenciales cuando utilizo el Consume Adapter Service complemento del proyecto de BizTalk o metadatos Asistente para agregar adaptador?  
 Cuando se usa el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para recuperar esquemas de mensaje para una solución de BizTalk, debe proporcionar un nombre de usuario y una contraseña para la base de datos de Oracle. Debe hacerlo desde el **seguridad** pestaña en el **configurar el adaptador** cuadro de diálogo. Esto garantiza que las credenciales no se mostrarán en el **configurar un URI** campo de la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] cuadro de diálogo, donde cualquier persona con acceso a la pantalla del equipo puede leer. Para obtener más información acerca de cómo recuperar esquemas de mensaje mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], incluida la forma de escribir un nombre de usuario y una contraseña para la base de datos de Oracle, vea [obtener metadatos para operaciones de Oracle en Visual Studio](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md).  
  
## <a name="how-do-i-protect-credentials-when-i-configure-a-send-port-or-a-receive-location"></a>¿Cómo se puede proteger las credenciales cuando configura un puerto de envío o una ubicación de recepción?  
 Las soluciones de BizTalk usan el adaptador personalizado de WCF de Microsoft BizTalk para consumir servicios WCF. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] es un enlace personalizado de WCF que permite a los clientes usar la base de datos de Oracle como si fuera un servicio WCF. Soluciones de BizTalk consumen la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] a través de puertos de envío y ubicaciones de recepción que están configurados para usar el adaptador de WCF-Custom, que a su vez, está, configurado para usar el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] como su transporte. Para obtener más información acerca de cómo configurar puertos de envío y puertos de recepción (ubicaciones de recepción), incluido cómo configurar el adaptador WCF-Custom, vea [configurar manualmente un enlace de puerto físico para el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/manually-configure-a-physical-port-binding-to-the-oracle-database-adapter.md).  
  
 Configurar las credenciales de la base de datos de Oracle desde la **credenciales** pestaña de la **propiedades de transporte de WCF-Custom** cuadro de diálogo para puertos de envío o de la **otros** pestaña de la **Propiedades de transporte de WCF-Custom** cuadro de diálogo para las ubicaciones de recepción. Dado que el adaptador WCF-Custom admite inicio de sesión único (SSO) empresarial, puede proporcionar un nombre de usuario y contraseña o una aplicación afiliada SSO en cualquiera de estas pestañas. Los temas siguientes describen ambas opciones.  
  
### <a name="user-name-password-credentials"></a>Credenciales de contraseña de nombre de usuario  
 Solo se deben proporcionar un nombre de usuario y una contraseña de la **credenciales** ficha (para los puertos de envío) o la **otros** ficha (para ubicaciones de recepción) en la **propiedades de transporte de WCF-Custom**cuadro de diálogo. Esto garantiza lo siguiente:  
  
-   Las credenciales no se mostrará en el **dirección (URI)** campo del cuadro de diálogo. Esto evita que aquellos que tienen acceso a la pantalla (o que tienen permisos que puedan ver el puerto de envío o propiedades de la ubicación de recepción) vean sus credenciales.  
  
-   La contraseña no se escribirán en el archivo de enlace si exporta el puerto de envío o recepción de enlace de puerto. Esto evita que cualquiera con acceso al archivo de ver la contraseña.  
  
### <a name="enterprise-single-sign-on-and-sso-affiliate-applications"></a>Aplicaciones afiliadas de SSO y Enterprise Single Sign-On  
 Puede configurar el adaptador de WCF-Custom para usar el inicio de sesión único empresarial (SSO) para obtener las credenciales para la base de datos de Oracle. SSO utiliza una base de datos y un secreto principal para cifrar y almacenar las credenciales de usuario. También proporciona servicios para asignar cuentas de Microsoft Windows a credenciales secundarias que se utilizan para tener acceso a un sistema back-end. Mediante el uso de SSO, puede asignar una cuenta de Windows a un nombre de usuario y una contraseña en la base de datos de Oracle.  
  
 SSO utiliza *aplicaciones afiliadas* y *asignaciones de SSO* para asignar las credenciales para el sistema back-end. Una aplicación afiliada es una entidad lógica de SSO que hace referencia a un sistema o una aplicación que requiera credenciales secundarias. Una asignación de SSO está asociada a una aplicación afiliada. Se asigna una cuenta de Windows a las credenciales secundarias usadas esa cuenta para tener acceso al sistema afiliado o la aplicación. Una asignación de SSO puede asociarse con una cuenta de usuario de Windows o con un grupo.  
  
 Usar SSO con el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], debe hacer lo siguiente.  
  
1.  Crear una aplicación afiliada de SSO para contener el usuario las credenciales de contraseña de nombre de la base de datos de Oracle. A menudo, este paso se realiza por una persona con tipos especiales de privilegios de administrador de SSO.  
  
2.  Crear un usuario o la asignación de grupos de la aplicación afiliada que se asigna la cuenta de Windows para el nombre de usuario y una contraseña que se utilizan para establecer una conexión con la base de datos de Oracle. Dependiendo de la instalación, un usuario podría ser capaz de realizar este paso o puede requerir una persona con tipos especiales de privilegios de administrador de SSO.  
  
> [!NOTE]
>  Cuando se configura para SSO, el adaptador WCF-Custom utiliza servicios proporcionados por SSO para obtener el nombre de usuario de Oracle y la contraseña de la base de datos SSO. Proporciona estas (sin cifrar) a la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], de modo que el adaptador puede abrir una conexión a la base de datos de Oracle. SSO no proporciona ningún cifrado o la protección a través de la conexión entre el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] y la base de datos de Oracle.  
  
 Para obtener información sobre cómo usar SSO, incluida la información sobre cómo crear aplicaciones afiliadas y asignaciones SSO, vea [mediante SSO](../../core/using-sso.md). Para obtener más información acerca de SSO, vea [implementar Enterprise Single Sign-On](../../core/implementing-enterprise-single-sign-on.md).  
  
## <a name="the-acceptcredentialsinuri-binding-property"></a>La propiedad de enlace AcceptCredentialsInUri  
 El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] superficies la **AcceptCredentialsInUri** propiedad de enlace. Esta propiedad determina si se permiten las credenciales de base de datos de Oracle en el URI de conexión. De forma predeterminada, **AcceptCredentialsInUri** es **false** y [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] produce una excepción si las credenciales se incluyen en el URI.  
  
 Esta propiedad aparece porque hay determinados escenarios de programación que se requieren las credenciales estén presentes en el URI de conexión. Nunca debe ser el caso cuando se está configurando un puerto de envío o una ubicación de recepción, o cuando se usa el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para recuperar los esquemas de mensaje desde el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. Se recomienda no establecer **AcceptCredentialsInUri** a **true**. Para obtener más información sobre la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] propiedades de enlace, consulte [configurar las propiedades de enlace de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).  
  
 El **AcceptCredentialsInUri** no está disponible en la propiedad de enlace [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] en el **enlace** ficha al configurar un WCF-Custom o WCF-OracleDB de recepción o puerto de envío. Para establecer el valor de la **AcceptCredentialsInUri** propiedad de enlace, debe abrir el archivo de enlaces de adaptador (archivo XML) que se crea después de haber generado los metadatos que utilizan el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]y, a continuación, busque esta propiedad de enlace en el archivo. Especifique un valor adecuado para esta propiedad de enlace, guarde el archivo de enlace y, a continuación, importe el archivo de enlace en el servidor BizTalk Server. Vea [enlaces del adaptador SQL reutilizar](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md).  
  
## <a name="see-also"></a>Vea también  
 [Proteger las aplicaciones de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/secure-your-oracle-database-applications.md)   
[Prácticas recomendadas](../../adapters-and-accelerators/adapter-oracle-database/best-practices-to-secure-the-oracle-database-adapter.md)