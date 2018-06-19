---
title: Crear un paquete de implementación con el SDK de adaptador LOB de WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10022981-7944-45d6-a78a-4d680a79b010
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 734d79e92a4864090720434b9a1fb83387a0a850
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966562"
---
# <a name="create-a-deployment-package-with-the-wcf-lob-adapter-sdk"></a>Crear un paquete de implementación con el SDK de adaptador LOB de WCF
Durante el ciclo de desarrollo, puede compilar, depurar y ejecutar el adaptador dentro de Visual Studio. El resultado de una solución de adaptador es un ensamblado DLL. Puede generar la solución de adaptador mediante el IDE de Visual Studio o usar los scripts de devenv.exe para crear un ensamblado del adaptador. Una vez que el adaptador se ha desarrollado y está listo para su uso en el entorno del consumidor de adaptador, debe crear un paquete de implementación que permite que el adaptador para instalarse en entornos de prueba y producción.  
  
 Puede incluir un proyecto de instalación de Visual Studio e implementación dentro de la solución. Esto se puede utilizar para generar automáticamente un archivo .msi como parte de la compilación de soluciones.  
  
> [!NOTE]
>  Puede impedir que el proyecto de instalación e implementación compilar cada vez que compile la solución en la estación de trabajo local mediante la exclusión mediante el Administrador de configuración (en el menú Generar) dentro de Visual Studio. NET. Si excluye un proyecto desde una compilación de soluciones con este método, no afectan el archivo de solución controlado de origen. Los cambios se mantienen en el archivo de opción de usuario de solución, que es específico del desarrollador y no se admite con control de código fuente.  
  
 Cada vez que se agregan nuevos proyectos a la solución debe acordarse de actualizar y configurar el proyecto de implementación para asegurarse de que la salida del nuevo proyecto se incluye en el archivo .msi y que se realicen los pasos de instalación específicos del proyecto.  
  
 No es suficiente instalar solo la salida del proyecto de adaptador en el equipo del usuario. El adaptador debe instalarse en la caché global de ensamblados (GAC) y el archivo machine.config debe actualizarse para registrar el adaptador con [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)].  
  
 Aquí te mostramos una acción personalizada de ejemplo que puede usarse para registrar o anular el registro de un adaptador con [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)].  
  
```  
using System;  
using System.Collections.Generic;  
using System.ComponentModel;  
using System.Configuration.Install;  
  
using System.Reflection;  
using System.ServiceModel.Configuration;  
using System.Diagnostics;  
using System.Configuration;  
  
namespace Microsoft.Adapters.Samples.EchoV2  
{  
    //Custom action to register the adapter with WCF configuration in machine.config   
  
    //<system.serviceModel>  
    //  <extensions>  
    //    <bindingElementExtensions>  
    //      <add name="{BINDINGELEM_NAME}" type="{BINDINGELEM_TYPE}, {Assembly Information}" />  
    //    </bindingElementExtensions>  
    //    <bindingExtensions>  
    //      <add name="{BINDING_NAME}" type="{BINDING_TYPE}, {Assembly Information}" />  
    //    </bindingExtensions>  
    //  </extensions>  
    //  <client>  
    //    <endpoint binding="{BINDING_NAME}" contract="IMetadataExchange" name="{BINDING_SCHEME}" />  
    //  </client>  
    //</system.serviceModel>  
  
    [RunInstaller(true)]  
    public partial class WCFLOBAdapterInstaller : Installer  
    {  
        private Assembly adapterAssembly;  
        private Type bindingSectionType;  
        private Type bindingElementExtensionType;  
        const string INSTALLER_PARM_INSTALLDIR = "INSTALLDIR";  
        const string BINDING_ASSEMBLY_NAME = "Microsoft.Adapters.Samples.EchoV2.EchoAdapter.dll";  
        const string BINDINGELEM_NAME = "echoAdapterV2";  
        const string BINDINGELEM_TYPE = "Microsoft.Adapters.Samples.EchoV2.EchoAdapterBindingElementExtensionElement";  
        const string BINDING_NAME = "echoAdapterBindingV2";  
        const string BINDING_TYPE = "Microsoft.Adapters.Samples.EchoV2.EchoAdapterBindingCollectionElement";  
        const string BINDING_SCHEME = "echov2";  
  
        /// <summary>  
        /// Constructor - initialize the components and register the event handlers  
        /// </summary>  
        public WCFLOBAdapterInstaller()  
        {  
            InitializeComponent();  
            this.AfterInstall += new InstallEventHandler(AfterInstallEventHandler);  
            this.BeforeUninstall += new InstallEventHandler(BeforeUninstallEventHandler);  
        }  
  
        /// <summary>  
        /// Add the WCF configuration information in machine.config when installing the adapter.  
        /// </summary>  
        /// <param name="sender"></param>  
        /// <param name="e"></param>  
        private void AfterInstallEventHandler(object sender, InstallEventArgs e)  
        {  
            try  
            {  
                Debug.Assert(this.Context != null, "Context of this installation is null.");  
                string path = this.Context.Parameters[INSTALLER_PARM_INSTALLDIR] + BINDING_ASSEMBLY_NAME;  
                adapterAssembly = Assembly.LoadFrom(path);  
                Debug.Assert(adapterAssembly != null, "Adapter assembly is null.");  
                bindingSectionType = adapterAssembly.GetType(BINDING_TYPE, true);  
                Debug.Assert(bindingSectionType != null, "Binding type is null.");  
                bindingElementExtensionType = adapterAssembly.GetType(BINDINGELEM_TYPE, true);  
                Debug.Assert(bindingElementExtensionType != null, "Binding element extension type is null.");  
                AddMachineConfigurationInfo();  
            }  
            catch (Exception ex)  
            {  
                throw new InstallException("Error while adding adapter configuration information. " + ex.InnerException.Message);  
            }  
        }  
  
        /// <summary>  
        /// Registers the adapter with the WCF configuration  
        /// NOTE: The   
        /// </summary>  
        public void AddMachineConfigurationInfo()  
        {  
            System.Configuration.Configuration config = ConfigurationManager.OpenMachineConfiguration();  
            Debug.Assert(config != null, "Machine.Config returned null");  
            // add <client><endpoint>               
            ServiceModelSectionGroup sectionGroup = config.GetSectionGroup("system.serviceModel") as ServiceModelSectionGroup;  
            if (sectionGroup != null)  
            {  
  
                bool channelEndpointElementExists = false;  
                // this call can throw an exception if there is problem   
                // loading endpoint configurations - e.g. each endpoint  
                // tries to load binding which in turn loads the DLL  
                ClientSection clientSection = sectionGroup.Client;  
                foreach (ChannelEndpointElement elem in clientSection.Endpoints)  
                {  
                    if (elem.Binding.Equals(BINDING_NAME, StringComparison.OrdinalIgnoreCase) && elem.Name.Equals(BINDING_SCHEME, StringComparison.OrdinalIgnoreCase) && elem.Contract.Equals("IMetadataExchange", StringComparison.OrdinalIgnoreCase))  
                    {  
                        channelEndpointElementExists = true;  
                        break;  
                    }  
                }  
                if (!channelEndpointElementExists)  
                {  
                    Debug.WriteLine("Adding ChannelEndpointElement for : " + BINDING_NAME);  
                    ChannelEndpointElement elem = new ChannelEndpointElement();  
                    elem.Binding = BINDING_NAME;  
                    elem.Name = BINDING_SCHEME;  
                    elem.Contract = "IMetadataExchange";  
                    sectionGroup.Client.Endpoints.Add(elem);  
                    Debug.WriteLine("Added ChannelEndpointElement for : " + BINDING_NAME);  
                }  
  
                // add <bindingElementExtension>  
                if (!sectionGroup.Extensions.BindingElementExtensions.ContainsKey(BINDINGELEM_NAME))  
                {  
                    ExtensionElement ext = new ExtensionElement(BINDINGELEM_NAME, bindingElementExtensionType.FullName + "," + bindingElementExtensionType.Assembly.FullName);  
                    sectionGroup.Extensions.BindingElementExtensions.Add(ext);  
                }  
  
                // add <bindingExtension>  
                if (!sectionGroup.Extensions.BindingExtensions.ContainsKey(BINDING_NAME))  
                {  
                    ExtensionElement ext = new ExtensionElement(BINDING_NAME, bindingSectionType.FullName + "," + bindingSectionType.Assembly.FullName);  
                    sectionGroup.Extensions.BindingExtensions.Add(ext);  
                }  
  
                config.Save();  
            }  
            else throw new InstallException("Machine.Config doesn't contain system.serviceModel node");  
        }  
  
        /// <summary>  
        /// Remove the machine configuration information when uninstalling the adapter  
        /// </summary>  
        /// <param name="sender"></param>  
        /// <param name="e"></param>  
        private void BeforeUninstallEventHandler(object sender, InstallEventArgs e)  
        {  
            try  
            {  
                RemoveMachineConfigurationInfo();  
            }  
            catch (Exception ex)  
            {  
                throw new InstallException("Error while removing adapter configuration information" + ex.InnerException.Message);  
            }  
        }  
  
        /// <summary>  
        /// Unregisters the adapter with WCF configuration  
        /// </summary>  
        public void RemoveMachineConfigurationInfo()  
        {  
            System.Configuration.Configuration config = ConfigurationManager.OpenMachineConfiguration();  
            Debug.Assert(config != null, "Machine.Config returned null");  
            ServiceModelSectionGroup sectionGroup = config.GetSectionGroup("system.serviceModel") as ServiceModelSectionGroup;  
            ChannelEndpointElement elemToRemove = null;  
            if (sectionGroup != null)  
            {  
                // Remove <client><endpoint>  
                foreach (ChannelEndpointElement elem in sectionGroup.Client.Endpoints)  
                {  
                    if (elem.Binding.Equals(BINDING_NAME, StringComparison.OrdinalIgnoreCase) && elem.Name.Equals(BINDING_SCHEME, StringComparison.OrdinalIgnoreCase) && elem.Contract.Equals("IMetadataExchange", StringComparison.OrdinalIgnoreCase))  
                    {  
                        elemToRemove = elem;  
                        break;  
                    }  
                }  
                if (elemToRemove != null)  
                {  
                    Debug.WriteLine("Removing ChannelEndpointElement for : " + BINDING_NAME);  
                    sectionGroup.Client.Endpoints.Remove(elemToRemove);  
                    Debug.WriteLine("Removed ChannelEndpointElement for : " + BINDING_NAME);  
                }  
                // Remove <bindingExtension> for this adapter  
                if (sectionGroup.Extensions.BindingExtensions.ContainsKey(BINDING_NAME))  
                {  
                    sectionGroup.Extensions.BindingExtensions.RemoveAt(BINDING_NAME);  
                }  
                // Remove <bindingElementExtension> for this adapter  
                if (sectionGroup.Extensions.BindingElementExtensions.ContainsKey(BINDINGELEM_NAME))  
                {  
                    sectionGroup.Extensions.BindingElementExtensions.RemoveAt(BINDINGELEM_NAME);  
                }  
                config.Save();  
            }  
            else  
            {  
                throw new InstallException("Machine.Config doesn't contain system.serviceModel node");  
            }  
        }  
  
        /// <summary>  
        /// Use this for testing outside of the Setup project  
        /// </summary>  
        /// <param name="assemblyDirectory">Directory where the adapter assembly is located</param>  
        public static void TestAddConfiguration(string assemblyDirectory)  
        {  
            WCFLOBAdapterInstaller action = new WCFLOBAdapterInstaller();  
            InstallContext context = new InstallContext();  
            // In the Setup project, this is set by selecting custom action  
            // and in Properties setting /INSTALLDIR="[TARGETDIR]\" for CustomActionData  
            context.Parameters.Add("INSTALLDIR", assemblyDirectory);  
            action.Context = context;  
            action.AfterInstallEventHandler(null, null);  
        }  
  
        /// <summary>  
        /// Use this for testing outside of the Setup project  
        /// </summary>  
        /// <param name="assemblyDirectory">Directory where the adapter assembly is located</param>  
        public static void TestRemoveConfiguration(string assemblyDirectory)  
        {  
            WCFLOBAdapterInstaller action = new WCFLOBAdapterInstaller();  
            InstallContext context = new InstallContext();  
            // In the Setup project, this is set by selecting custom action  
            // and in Properties setting /INSTALLDIR="[TARGETDIR]\" for CustomActionData  
            context.Parameters.Add("INSTALLDIR", assemblyDirectory);  
            action.Context = context;  
            action.BeforeUninstallEventHandler(null, null);  
        }  
    }  
}  
```  
  
 Si desea explorar un adaptador de ejemplo con un paquete de implementación, puede descargar un adaptador de eco completado incluidos script de instalación y el código de prueba. En este ejemplo se incluye con los archivos de instalación de BizTalk en `\BizTalk Server\ASDK_x86\Program Files\WCF LOB Adapter SDK\Documents\Samples` o `\BizTalk Server\ASDK_x64\Program Files\WCF LOB Adapter SDK\Documents\Samples`.
  
## <a name="see-also"></a>Vea también  
 [Implementar un adaptador mediante el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/deploy-an-adapter-using-the-wcf-lob-adapter-sdk.md)   
 [Anular la implementación de un adaptador mediante el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/undeploy-an-adapter-using-the-wcf-lob-adapter-sdk.md)