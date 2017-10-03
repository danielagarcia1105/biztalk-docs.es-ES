---
title: Seguridad con el adaptador de SQL y el servidor de BizTalk | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc439d65-1d7e-4e6e-bb0d-a8cb9f0607b8
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b0bc410a651c179daf43c47fb573d1772f6c1e01
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="security-with-the-sql-adapter-and-biztalk-server"></a>Seguridad con el adaptador de SQL y BizTalk Server
Al configurar un puerto de envío o un puerto de recepción (ubicación) mediante el uso de la administración de BizTalk Server de la consola o utilizar el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para recuperar esquemas de mensaje para una solución de BizTalk, debe proporcionar credenciales para la base de datos de SQL Server. Es importante proporcionar estas credenciales de una manera segura para ayudar a evitar que se revelen a actores potencialmente malintencionados. Este tema describe cómo proporcionar una forma más segura de credenciales para el [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] para soluciones de BizTalk Server.  
  
 Una descripción más general de seguridad en el contexto de las soluciones de BizTalk es un tema amplio y queda fuera del ámbito de esta documentación. Para obtener información acerca de cómo hacer que las soluciones de BizTalk más segura, consulte [seguro y proteger los mensajes de BizTalk](../../core/secure-and-protect-your-biztalk-messages.md).
  
## <a name="how-do-i-protect-credentials-when-i-use-the-consume-adapter-service-biztalk-project-add-in"></a>¿Cómo proteger las credenciales cuando utilizo el Consume Adapter Service complemento del proyecto de BizTalk?  
 Cuando se usa el [!INCLUDE[consumeadapterservshort_md](../../includes/consumeadapterservshort-md.md)] para recuperar esquemas de mensaje para una solución de BizTalk, debe proporcionar el nombre de usuario y la contraseña de la **seguridad** pestaña en el **configurar el adaptador** cuadro de diálogo. El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] no le permitirá establecer credenciales en el **configurar un URI** campo. Esto mejora la seguridad al impedir que las credenciales que aparecen en texto no cifrado. Para obtener más información acerca de cómo recuperar esquemas de mensaje mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], incluida la forma de escribir un nombre de usuario y una contraseña para la base de datos de SQL Server, consulte [obtener los metadatos de las operaciones de SQL Server en Visual Studio mediante el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md).  
  
## <a name="how-do-i-protect-credentials-when-i-configure-a-send-port-or-a-receive-location"></a>¿Cómo se puede proteger las credenciales cuando configura un puerto de envío o una ubicación de recepción?  
 Las soluciones de BizTalk usan el adaptador personalizado de WCF de Microsoft BizTalk para consumir servicios WCF. El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] es un enlace personalizado de WCF que permite a los clientes usar la base de datos de SQL Server como si fuera un servicio WCF. Soluciones de BizTalk consumen la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] a través de puertos de envío y ubicaciones de recepción que están configurados para usar el adaptador WCF-Custom. El adaptador WCF-Custom, a su vez, va a usar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] como su transporte. Para obtener más información acerca de cómo configurar puertos de envío y puertos de recepción (ubicaciones de recepción), incluido cómo configurar el adaptador WCF-Custom, vea [configurar manualmente un enlace de puerto físico para el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md).
  
 Configurar las credenciales de la base de datos de SQL Server desde el **credenciales** pestaña de la **propiedades de transporte de WCF-Custom** cuadro de diálogo para puertos de envío o de la **otros** ficha de el **propiedades de transporte de WCF-Custom** cuadro de diálogo para las ubicaciones de recepción. Dado que el adaptador WCF-Custom admite inicio de sesión único (SSO) empresarial, también puede proporcionar un nombre de usuario y contraseña o una aplicación afiliada SSO en cualquiera de estas pestañas. Los temas siguientes describen ambas opciones.  
  
### <a name="user-name-password-credentials"></a>Credenciales de contraseña de nombre de usuario  
 Solo se deben proporcionar un nombre de usuario y una contraseña de la **credenciales** ficha (para los puertos de envío) o la **otros** ficha (para ubicaciones de recepción) en la **propiedades de transporte de WCF-Custom**cuadro de diálogo. Esto garantiza lo siguiente:  
  
-   Las credenciales no se mostrará en el **dirección (URI)** campo del cuadro de diálogo. Esto evita que aquellos que tienen acceso a la pantalla (o que tienen permisos que puedan ver el puerto de envío o propiedades de la ubicación de recepción) vean sus credenciales.  
  
-   La contraseña no se escribirán en el archivo de enlace si exporta el puerto de envío o recepción de enlace de puerto. Esto impide que cualquier persona con acceso al archivo de visualización de la contraseña.  
  
### <a name="enterprise-single-sign-on-and-sso-affiliate-applications"></a>Aplicaciones afiliadas de SSO y Enterprise Single Sign-On  
 Puede configurar el adaptador de WCF-Custom para que utilice el inicio de sesión único empresarial (SSO) para obtener las credenciales para la base de datos de SQL Server. SSO utiliza una base de datos y un secreto principal para cifrar y almacenar las credenciales de usuario. También proporciona servicios para asignar cuentas de Microsoft Windows a credenciales secundarias que se utilizan para tener acceso a un sistema back-end. Mediante el uso de SSO, puede asignar una cuenta de Windows a un nombre de usuario y una contraseña en la base de datos de SQL Server.  
  
 SSO utiliza *aplicaciones afiliadas* y *asignaciones de SSO* para asignar las credenciales para el sistema back-end. Una aplicación afiliada es una entidad lógica de SSO que hace referencia a un sistema o una aplicación que requiera credenciales secundarias. Una asignación de SSO está asociada a una aplicación afiliada. Se asigna una cuenta de Windows a las credenciales secundarias usadas esa cuenta para tener acceso al sistema afiliado o la aplicación. Una asignación de SSO puede asociarse con una cuenta de usuario de Windows o con un grupo.  
  
 Usar SSO con el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], debe hacer lo siguiente.  
  
1.  Crear una aplicación afiliada de SSO para contener el usuario las credenciales de contraseña de nombre de la base de datos de SQL Server. A menudo, este paso se realiza por una persona con tipos especiales de privilegios de administrador de SSO.  
  
2.  Crear un usuario o una asignación de grupo para la aplicación afiliada que se asigna la cuenta de Windows para el nombre de usuario y la contraseña que se utilizan para establecer una conexión con la base de datos de SQL Server. Dependiendo de la instalación, un usuario podría ser capaz de realizar este paso, o puede requerir una persona con tipos especiales de privilegios de administrador de SSO.  
  
> [!NOTE]
>  Cuando se configura para SSO, el adaptador WCF-Custom utiliza servicios proporcionados por SSO para obtener el nombre de usuario de SQL Server y la contraseña de la base de datos SSO. Proporciona estas (sin cifrar) a la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], de modo que el adaptador puede abrir una conexión a la base de datos de SQL Server. SSO no proporciona ningún cifrado o la protección a través de la conexión entre el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] y la base de datos de SQL Server.  
  
 Para obtener información sobre cómo usar SSO, incluida la información sobre cómo crear aplicaciones afiliadas y asignaciones SSO, vea [mediante SSO](../../core/using-sso.md). Para obtener más información acerca de SSO, vea [implementar Enterprise Single Sign-On](../../core/implementing-enterprise-single-sign-on.md).
  
## <a name="the-acceptcredentialsinuri-binding-property"></a>La propiedad de enlace AcceptCredentialsInUri  
 El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] no admite **AcceptCredentialsInUri** propiedad de enlace. Las credenciales no se permiten en el URI de conexión.  
  
## <a name="see-also"></a>Vea también  
[Proteger las aplicaciones de SQL](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md)  
[Prácticas recomendadas para proteger el adaptador de SQL](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md)