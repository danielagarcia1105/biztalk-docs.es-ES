---
title: Procedimientos recomendados para implementar una aplicación de BizTalk | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- best practices, deploying
- best practices, applications
- applications, best practices
- deploying, best practices
ms.assetid: 97ebf479-0dc5-4e95-b409-d3b6ad3d60d0
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3b50ff0a6e64633090e562b6ca8e3ae66eb8683
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233068"
---
# <a name="best-practices-for-deploying-a-biztalk-application"></a>Prácticas recomendadas para implementar una aplicación de BizTalk
En este tema se describen las prácticas recomendadas para implementar una aplicación de BizTalk.  
  
## <a name="group-related-artifacts-together-in-a-single-application"></a>Agrupar los artefactos relacionados en una única aplicación  
 Cuando sea posible, coloque los artefactos relacionados en la misma aplicación de BizTalk. Esto le permite administrar e implementar los artefactos como entidad individual, lo que facilita la administración. Puede agrupar artefactos que admitan los mismos artefactos o el mismo proceso empresarial que realicen funciones similares en una única aplicación.  
  
## <a name="deploy-shared-artifacts-in-a-separate-application"></a>Implementar artefactos compartidos en una aplicación diferente  
 Si dos o más aplicaciones van a compartir los artefactos, implemente los artefactos compartidos en una aplicación diferente. Por ejemplo, si dos aplicaciones comparten un esquema, coloque el esquema en una aplicación diferente. Esto se debe a que en un grupo de BizTalk solo puede existir un artefacto que tenga el mismo identificador local único (LUID), que consta del nombre del artefacto y, opcionalmente, otros atributos. Si incluye un artefacto en una aplicación y luego le crea una referencia desde otra aplicación, puede tener problemas, como que la aplicación a la que se hace referencia no funcione correctamente cuando detenga la aplicación que contiene el artefacto.  
  
 Estas prácticas recomendadas se aplican a todos los tipos de artefactos, salvo para archivos, como las secuencias de comandos y los archivos Léame, que se agregan a la aplicación como un tipo de archivo del artefacto. Esto se debe a que se puede implementar más de un artefacto de archivo que tenga el mismo nombre en un grupo de BizTalk. Por lo tanto, puede utilizar un archivo que tenga el mismo nombre en dos aplicaciones o más. Detener una aplicación no afectará a la otra aplicación. Para obtener más información acerca de cómo agregar artefactos de archivo, consulte [cómo agregar un archivo a una aplicación](../core/how-to-add-a-file-to-an-application.md).  
  
 Para obtener prácticas recomendadas acerca de cómo compartir tipos de artefactos específicos, consulte "Implementar un sitio Web compartido en una aplicación diferente", "Implementar directivas compartidas en una aplicación diferente" y "Implementar certificados compartidos en una aplicación diferente" de esta sección.  
  
## <a name="deploy-a-shared-web-site-in-a-separate-application"></a>Implementar un sitio Web compartido en una aplicación diferente  
 Si una o varias soluciones empresariales van a compartir un sitio Web, implemente el sitio Web en una aplicación diferente. Esto se debe a que cuando desinstala una aplicación de BizTalk, se quita el directorio virtual del sitio Web que forma parte de la aplicación, aunque se esté ejecutando el sitio Web. Si se comparte el sitio Web con otra solución empresarial, el resultado será que la otra solución empresarial dejará de funcionar correctamente.  
  
## <a name="deploy-shared-policies-in-a-separate-application"></a>Implementar directivas compartidas en una aplicación diferente  
 Si una o varias aplicaciones utilizan una directiva, debería implementarla en una aplicación diferente en lugar de crear una referencia de una aplicación a otra. Esto se debe a que cuando detiene la aplicación, se anula la implementación de sus directivas. Si detiene una aplicación que contiene una directiva que utiliza otra aplicación, la directiva dejará de funcionar en las dos aplicaciones.  
  
## <a name="deploy-shared-certificates-in-a-separate-application"></a>Implementar certificados compartidos en una aplicación diferente  
 Si una ubicación de recepción o un puerto de envío utiliza un certificado en dos o varias aplicaciones, debería implementar el certificado en una aplicación diferente y, a continuación, hacer referencia a esta aplicación desde las aplicaciones que necesitan utilizar el certificado. Esto se debe a que en un grupo de BizTalk solo puede existir un artefacto que tenga un LUID determinado, por lo que no podrá importar el mismo cerificado de dos aplicaciones diferentes. Si intenta importar dos aplicaciones que utilicen el mismo certificado, la primera importación se realizará correctamente, pero la segunda no. En este caso, la utilización de la opción Sobrescribir importación no soluciona el problema, ya que otra aplicación contiene el certificado existente que desea sobrescribir.  
  
## <a name="never-deploy-an-assembly-from-visual-studio-on-a-production-computer"></a>No implementar nunca un ensamblado en un equipo de producción desde Visual Studio.  
 Durante el proceso de desarrollo, el programador suele volver a implementar ensamblados de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]. Para permitir que se pueda volver a implementar, [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] debe anular la implementación, separar, detener y dar de baja artefactos que están contenidos en los ensamblados. Aunque esto resulta necesario y apropiado en un entorno de desarrollo, puede producir consecuencias inesperadas no deseadas en un entorno de producción. Por esta razón, y para evitar que alguien intente implementar un ensamblado desde [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] en un equipo de producción, se recomienda que nunca instale [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] en un equipo de producción.  
  
 Asimismo, no haga referencia nunca a una base de datos de producción desde un equipo que ejecute [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
## <a name="when-deploying-large-msi-files-you-may-need-to-increase-the-default-transaction-timeout-of-the-com-components-used-by-biztalk-to-deploy-applications"></a>Cuando implementa archivos MSI grandes, necesita aumentar el tiempo de espera predeterminado de la transacción de los componentes COM+ que utiliza BizTalk para implementar aplicaciones.  
 Si el archivo MSI que se implementa es muy largo (más de 100 MB), puede que la aplicación no se implemente en el tiempo de espera predeterminado de la transacción de los componentes COM+ que utiliza BizTalk durante la implementación de la aplicación. Si las transacciones asociadas con estos componentes COM+ agotan el tiempo de espera antes de que se haya completado la implementación, se producirá un error en la implementación. Si implementa archivos MSI muy grandes, tenga en cuenta realizar uno de estos enfoques para mitigar este problema:  
  
1.  Implemente varios archivos MSI pequeños en lugar de un único archivo MSI.  
  
2.  Aumentar el tiempo de espera de transacción predeterminado de 3.000 segundos asociada a la **Microsoft.BizTalk.ApplicationDeployment.Group** y **Microsoft.BizTalk.Deployment.DeployerComponent** componentes de la **servicios de componentes** interfaz de administración. Estos componentes pertenecen a la **Microsoft.BizTalk.ApplicationDeployment.Engine** y **Microsoft.Biztalk.Deployment** aplicaciones COM + respectivamente. Para obtener más información sobre cómo cambiar la transacción vea el valor de tiempo de espera para un componente COM + [cómo cambiar el valor de tiempo de espera de transacción para MTS o COM +](http://go.microsoft.com/fwlink/?LinkId=67691).  
  
## <a name="see-also"></a>Vea también  
 [Implementar y administrar aplicaciones de BizTalk](../core/deploying-and-managing-biztalk-applications.md)