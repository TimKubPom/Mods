# main
package kingoffire.common;

import kingoffire.blocks.JadeeBlock;

import kingoffire.tileentity.TileEntityJadee;

import net.minecraft.block.Block;
import net.minecraft.block.material.Material;

import cpw.mods.fml.client.registry.ClientRegistry;
import cpw.mods.fml.client.registry.RenderingRegistry;
import cpw.mods.fml.common.Mod;
import cpw.mods.fml.common.Mod.EventHandler;
import cpw.mods.fml.common.Mod.Init;
import cpw.mods.fml.common.Mod.Instance;
import cpw.mods.fml.common.SidedProxy;
import cpw.mods.fml.common.event.*;
import cpw.mods.fml.common.network.NetworkMod;
import cpw.mods.fml.common.registry.*;
import cpw.mods.fml.relauncher.Side;
import cpw.mods.fml.relauncher.SideOnly;

@Mod (modid = "KingOfFireMod" ,name = "King Of Fire Mod" ,version = "1.0 Alpha")
@NetworkMod(clientSideRequired = true, serverSideRequired = false)

public class KingOfFireMod {
	
     @SidedProxy(clientSide="kingoffire.client.ClientProxy", serverSide="kingoffire.common.CommonProxy")
	  public static CommonProxy proxy;
     
     //Block
	  
	  public static Block blockJadee = new JadeeBlock(2500).setUnlocalizedName("Jadee");
	 
@Init
public void load(FMLInitializationEvent event)
{
  proxy.registerRenderInformation();
}
  public KingOfFireMod()
  {
	  
//Blocks	
GameRegistry.registerBlock(blockJadee, "Jadee");

GameRegistry.registerTileEntity(TileEntityJadee.class, "Jadee");

//Blocks
LanguageRegistry.addName(blockJadee, "Jadee");

    }

  }




	



