---
title: Seguridad con el adaptador de Oracle E-Business Suite y BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7d4a816c-505d-4d5d-9eb9-04847f9b5861
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe73785ee49b260754a35e27f8ffa2ef2bcaa6bb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218484"
---
# <a name="security-with-the-oracle-e-business-suite-adapter-and-biztalk-server"></a>Seguridad con el adaptador de Oracle E-Business Suite y BizTalk Server
Al configurar un puerto de envío o un puerto de recepción (ubicación) mediante el uso de la administración de BizTalk Server de la consola o utilizar el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para recuperar esquemas de mensaje para una solución de BizTalk, debe proporcionar credenciales para Oracle E-Business Suite. Es importante proporcionar estas credenciales de una manera segura para ayudar a evitar que se revelen a actores potencialmente malintencionados. Este tema describe cómo proporcionar una forma más segura de credenciales para el [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] para soluciones de BizTalk Server.  
  
 Una descripción más general de seguridad en el contexto de las soluciones de BizTalk es un tema amplio y queda fuera del ámbito de esta documentación. Para obtener información acerca de cómo hacer que las soluciones de BizTalk más segura, consulte [seguro y proteger los mensajes de BizTalk](../../core/secure-and-protect-your-biztalk-messages.md).   
  
## <a name="how-do-i-protect-credentials-when-i-use-the-consume-adapter-service-biztalk-project-add-in-or-add-adapter-metadata-wizard"></a>¿Cómo proteger las credenciales cuando utilizo el Consume Adapter Service complemento del proyecto de BizTalk o metadatos Asistente para agregar adaptador?  
 Cuando se usa el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] para recuperar esquemas de mensaje para una solución de BizTalk, puede proporcionar credenciales para conectarse a Oracle E-Business Suite en las dos ubicaciones siguientes:  
  
-   En el **seguridad** pestaña en el **configurar el adaptador** cuadro de diálogo. Esto garantiza que las credenciales no se mostrarán en el **configurar un URI** campo de la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] cuadro de diálogo, donde cualquier persona con acceso a la pantalla del equipo puede leer.  
  
-   En el **OracleUserName** y **OraclePassword** propiedades de enlace el **propiedades de enlace** pestaña en el **configurar el adaptador** cuadro de diálogo. Por motivos de seguridad, el **OraclePassword** propiedad de enlace no disponible del archivo de enlace XML (archivo) generado como resultado de utilizar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].  
  
    > [!NOTE]
    >  Mediante el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] no genera ningún archivo de enlace.  
  
 Para obtener más información acerca de cómo recuperar esquemas de mensaje mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], consulte [obtener metadatos para operaciones de Oracle E-Business Suite en Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md).  
  
## <a name="how-do-i-protect-credentials-when-i-configure-a-send-port-or-a-receive-location"></a>¿Cómo se puede proteger las credenciales cuando configura un puerto de envío o una ubicación de recepción?  
 Soluciones de BizTalk usan el adaptador de Microsoft BizTalk WCF-Custom o WCF Oracle EBS para consumir servicios WCF. El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] es un enlace WCF que permite a los clientes utilizar Oracle E-Business Suite como si fuera un servicio WCF. Soluciones de BizTalk consumen la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] a través de puertos de envío y ubicaciones de recepción que están configurados para usar el adaptador WCF-Custom o WCF-OracleEBS, que a su vez, está, configurado para usar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] como su transporte. Para obtener más información acerca de cómo configurar puertos de envío y puertos de recepción (ubicaciones de recepción), incluido cómo configurar el adaptador WCF-Custom, vea [configurar un enlace de puerto físico mediante un archivo de enlace de puerto a la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md).  
  
 Configurar las credenciales de Oracle E-Business Suite desde el **credenciales** pestaña de la **propiedades de transporte de WCF-Custom** cuadro de diálogo para puertos de envío o de la **otros** pestaña de la **propiedades de transporte de WCF-Custom** cuadro de diálogo para las ubicaciones de recepción. Dado que el adaptador de WCF-Custom o WCF Oracle EBS admite inicio de sesión único (SSO) empresarial, puede elegir proporcionar un nombre de usuario y una contraseña o aplicación en cualquiera de estas pestañas afiliado de SSO. Los temas siguientes describen ambas opciones.  
  
### <a name="user-name-password-credentials"></a>Credenciales de contraseña de nombre de usuario  
 Solo se deben proporcionar un nombre de usuario y una contraseña de la **credenciales** ficha (para los puertos de envío) o la **otros** ficha (para ubicaciones de recepción) en la **propiedades de transporte de WCF-Custom**cuadro de diálogo. Esto garantiza lo siguiente:  
  
-   Las credenciales no se mostrará en el **dirección (URI)** campo del cuadro de diálogo. Esto evita que aquellos que tienen acceso a la pantalla (o que tienen permisos que puedan ver el puerto de envío o propiedades de la ubicación de recepción) vean sus credenciales.  
  
-   La contraseña no se escribirán en el archivo de enlace si exporta el puerto de envío o recepción de enlace de puerto. Esto evita que cualquiera con acceso al archivo de ver la contraseña.  
  
### <a name="oraclepassword-binding-property"></a>Propiedad de enlace de OraclePassword  
 El valor que especifique en el **OraclePassword** enlace de propiedad para el envío o recepción puerto está disponible en texto no cifrado al exportar enlaces desde una aplicación de BizTalk Server. Por lo tanto, después de exportar un archivo de enlace de una aplicación de BizTalk Server, debe quitar manualmente el valor de la **OraclePassword** propiedad de enlace desde el archivo de enlace y, a continuación, especifíquelo de nuevo en cada host donde la se usará el enlace exportado.  
  
### <a name="enterprise-single-sign-on-and-sso-affiliate-applications"></a>Aplicaciones afiliadas de SSO y Enterprise Single Sign-On  
 Puede configurar el adaptador de WCF-Custom para usar el inicio de sesión único empresarial (SSO) para obtener las credenciales para Oracle E-Business Suite. SSO utiliza una base de datos y un secreto principal para cifrar y almacenar las credenciales de usuario. También proporciona servicios para asignar cuentas de Microsoft Windows a credenciales secundarias que se utilizan para tener acceso a un sistema back-end. Mediante el uso de SSO, puede asignar una cuenta de Windows a un nombre de usuario y una contraseña en la base de datos de Oracle.  
  
 SSO utiliza *aplicaciones afiliadas* y *asignaciones de SSO* para asignar las credenciales para el sistema back-end. Una aplicación afiliada es una entidad lógica de SSO que hace referencia a un sistema o una aplicación que requiera credenciales secundarias. Una asignación de SSO está asociada a una aplicación afiliada. Se asigna una cuenta de Windows a las credenciales secundarias usadas esa cuenta para tener acceso al sistema afiliado o la aplicación. Una asignación de SSO puede asociarse con una cuenta de usuario de Windows o con un grupo.  
  
 Usar SSO con el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], debe hacer lo siguiente.  
  
1.  Crear una aplicación afiliada de SSO para contener credenciales de contraseña de nombre de usuario para Oracle E-Business Suite. A menudo, este paso se realiza por una persona con tipos especiales de privilegios de administrador de SSO.  
  
2.  Crear un usuario o la asignación de grupos de la aplicación afiliada que se asigna la cuenta de Windows para el nombre de usuario y una contraseña que se utilizan para establecer una conexión con la base de datos de Oracle. Dependiendo de la instalación, un usuario podría ser capaz de realizar este paso o puede requerir una persona con tipos especiales de privilegios de administrador de SSO.  
  
> [!NOTE]
>  Cuando se configura para SSO, el adaptador WCF-Custom utiliza servicios proporcionados por SSO para obtener el nombre de usuario de Oracle y la contraseña de la base de datos SSO. Proporciona estas (sin cifrar) a la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], de modo que el adaptador puede abrir una conexión a Oracle E-Business Suite. SSO no proporciona ningún cifrado o la protección a través de la conexión entre el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] y Oracle E-Business Suite.  
  
 Para obtener información sobre cómo usar SSO, incluida la información sobre cómo crear aplicaciones afiliadas y asignaciones SSO, vea [mediante SSO](../../core/using-sso.md). Para obtener más información acerca de SSO, vea [implementar Enterprise Single Sign-On](../../core/implementing-enterprise-single-sign-on.md). 
  
## <a name="the-acceptcredentialsinuri-binding-property"></a>La propiedad de enlace AcceptCredentialsInUri  
 El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] superficies la **AcceptCredentialsInUri** propiedad de enlace. Esta propiedad determina si la base de datos de Oracle o credenciales de Oracle E-Business Suite se permiten en el URI de conexión. De forma predeterminada, **AcceptCredentialsInUri** es **false** y [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] produce una excepción si las credenciales se incluyen en el URI.  
  
 Esta propiedad aparece porque hay determinados escenarios de programación que se requieren las credenciales estén presentes en el URI de conexión. Nunca debe ser el caso cuando se está configurando un puerto de envío o una ubicación de recepción, o cuando se usa el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para recuperar los esquemas de mensaje desde el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]. Se recomienda no establecer **AcceptCredentialsInUri** a **true**. Para obtener más información sobre la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] propiedades de enlace, consulte [obtener información sobre el adaptador de BizTalk para propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md).  
  
 El **AcceptCredentialsInUri** no está disponible en la propiedad de enlace [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] en el **enlace** ficha al configurar un WCF-Custom o WCF-OracleEBS de recepción o puerto de envío. Para establecer el valor de la **AcceptCredentialsInUri** propiedad de enlace, debe abrir el archivo de enlaces de adaptador (archivo XML) que se crea después de haber generado los metadatos que utilizan el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]y, a continuación, busque esta propiedad de enlace en el archivo. Especifique un valor adecuado para esta propiedad de enlace, guarde el archivo de enlace y, a continuación, importe el archivo de enlace en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]. Vea [importar enlaces](http://msdn.microsoft.com/library/7af35a2e-fb7c-48a1-af28-93427403a745) para obtener instrucciones.  
  
## <a name="see-also"></a>Vea también  
 [Proteger las aplicaciones de Oracle EBS](../../adapters-and-accelerators/adapter-oracle-ebs/secure-your-oracle-ebs-applications.md)  
 [Prácticas recomendadas para proteger el adaptador de Oracle EBS](../../adapters-and-accelerators/adapter-oracle-ebs/best-practices-to-secure-the-oracle-e-business-suite-adapter.md)
