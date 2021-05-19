# sistema-
um CRUD em PHP e MSQL com BOOTSTRAP
contendo as seguintes informações 
nome (input text)
telefone (input text)
email (input text)
cidade (input text)
estado (select box)
categoria (select box com os itens Cliente, Fornecedor e Funcionário)

________ aqui vai o código da aplicação __________________________________________________________________________________________

( interface)
 nome do arquivo index.php


<?php 
  include ("conexao.php");
 ?>

<!DOCTYPE html>
<html lang="pt-Br">
<head>
    <meta charset="utf-8">
    <title>formulário de cadastro</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.1/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-+0n0xVW2eSR5OomGNYDnhzAbDsOXxcvSN1TPprVMTNDbiYZCxYbOOl7+AMvyTG2x" crossorigin="anonymous">
   

    <style type="text/css">
           
           #tamanhoContainer{
          width: 500px;
           }

           #botao{
           
           background-color: #73d450; /*aqui a cor de fundo - #FF1168- Ana Caroline Sardinha Tavares  */
           color: #ffffff;    /* aqui cor da letra   email: ana.carolina100392@gmail.ccom   */
           font-weight: bold;

           }

 </style>



</head>


<body>
      

    <div  class="container"  id="tamanhoContainer"   style="margin-top:40px ">
    
          <h4> &nbsp &nbsp &nbsp  &nbsp &nbsp  &nbsp Minha Agenda De Registros</h4>


    <form  action="_inserir_nome.php"  method="post" style="margin-top: 20px">
            <div class="form-group">
            <label>Nome</label>
            <input type="text" class="form-control" name="Nome" placeholder="Digite Seu Nome" required>

            </div>
      
            <div class="form-group">
            <label>Telefone</label>
            <input type="text" class="form-control"  name="Telefone"  placeholder="Insira o Número de Telefone" required>

            </div>



           <div class="form-group">
            <label>Cidade</label>
            <input type="text" class="form-control"  name="Cidade" placeholder="Digite Sua Cidade" required>

            </div>

  <div class="form-group">
      <label>Estado</label>
      <select class="form-control" name="Estado">
        <option>Seleção</option>
        <option>Acre (AC)</option>
        <option>Alagoas (AL)</option>
        <option>Amapá (AP)</option>
        <option>Amazonas (AM)</option>
        <option>Bahia (BA)</option>
        <option>Ceará (CE)</option>
        <option>Distrito Federal (DF)</option>
        <option>Espírito Santo (ES)</option>
        <option>Goiás (GO)</option>
        <option>Maranhão (MA)</option>
        <option>Mato Grosso (MT)</option>
        <option>Mato Grosso do Sul (MS)</option>
        <option>Minas Gerais (MG)</option>
        <option>Pará (PA)</option>
        <option>Paraíba (PB)</option>
        <option>Paraná (PR)</option>
        <option>Pernambuco (PE)</option>
        <option>Piauí (PI)</option>
        <option>Rio de Janeiro (RJ)</option>
        <option>Rio Grande do Norte (RN)</option>
        <option>Rio Grande do Sul (RS)</option>
        <option>Rondônia (RO)</option>
        <option>Roraima (RR)</option>
        <option>Santa Catarina (SC)</option>
        <option>São Paulo (SP)</option>
        <option>Sergipe (SE)</option>
        <option>Tocantins (TO)</option>
      </select>

       <br>
       <p>Tipo de cadastro:</p>

    
         <div class="custom-control custom-checkbox">
             <input type="radio" class="custom-control-input" name="tipocadastro" id="customCheck1"
              value="Cliente">
             <label class="custom-control-label" for="customCheck1">Cliente</label>
</div>


        <div class="custom-control custom-checkbox">
             <input type="radio" class="custom-control-input"  name="tipocadastro" id="customCheck2"
             value="Fornecedor">
             <label class="custom-control-label" for="customCheck1">Fornecedor</label>
</div>


       <div class="custom-control custom-checkbox">
            <input type="radio" class="custom-control-input" name="tipocadastro"  id="customCheck3"
            value="Funcionário">
            <label class="custom-control-label" for="customCheck1">Funcionário</label>


  </div> 
  <div style="text-align: right;">
  <button type="submit"  id="botao" class="btn  btn-sm">Cadastrar</button>
</div>
</form>
</div>





<script src="https://code.jquery.com/jquery-3.2.1.slim.min.js" integrity="sha384-KJ3o2DKtIkvYIK3UENzmM7KCkRr/rE9/Qpg6aAZGJwFDMVNA/GpGFF93hXpG5KkN" crossorigin="anonymous"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.12.9/umd/popper.min.js" integrity="sha384-ApNbgh9B+Y1QKtv3Rn7W3mgPxhU9K/ScQsAP7hUibX39j7fakFPskvXusvfa0b4Q" crossorigin="anonymous"></script>
<script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/js/bootstrap.min.js" integrity="sha384-JZR6Spejh4U02d8jOt6vLEHfe/JQGiRRSQQxSfFWpi1MquVdAyjUar5+76PVCmYl" crossorigin="anonymous"></script>

</body>
</html>
  
  _______________________________________________________________________________________________________
  listar_nome.php                           /nome do arquivo
  _______________________________________________________________________________________________________
  <!DOCTYPE html>
<html lang="pt-BR">
<head>
  <title>listagem de nome</title>

<meta charset="utf-8">

<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.1/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-+0n0xVW2eSR5OomGNYDnhzAbDsOXxcvSN1TPprVMTNDbiYZCxYbOOl7+AMvyTG2x" crossorigin="anonymous">
<script src="https://kit.fontawesome.com/e50dbee61b.js" crossorigin="anonymous"></script></head>
<body>


<div class="container"  style="margin-top: 40px">
<h3>listar nomes</h3>
<br>




<table class="table">
  <thead>
    <tr>
      <th scope="col">nome</th>
      <th scope="col">telefone</th>
      <th scope="col">cidade</th>
      <th scope="col">estado</th>
      <th scope="col">registro</th>
      <th scope="col">cliente</th>
      <th scope="col">fornecedor</th>
      <th scope="col">funcionário</th>
       <th scope="col">Ação</th>

    </tr>
 </thead>
 

    <?php
     
         include 'conexao.php';
         $sql="SELECT * FROM `curso`";
         $busca = mysqli_query($conexao,$sql);
         
         while ($array = mysql_fetch_array(busca)) {
           
                $cadastroID = $arry['cadastroID'];
                $nome = $arry['nome'];
                $telefone = $arry['telefone'];
                $cidade = $arry['cidade'];
                $estado = $arry['estado'];
                $registro = $arry['registro'];
                $cliente = $arry['cliente'];
                $fornecedor = $arry['fornecedor'];
                $funcionario = $arry['funcionario'];


?>                                                                                                                                             

   <tr>

      <td><?php echo $nome;?></td>

      <td><?php echo $telefone;?></td>

      <td><?php echo $cidade;?></td>

      <td><?php echo $estado;?></td>

      <td><?php echo $registro;?></td>

      <td><?php echo $cliente;?></td>

      <td><?php echo $fornecedor;?></td>

      <td><?php echo $funcionario;?></td>

      <td><<a class="btn btn-warning"  style="color: #fff"   href="editar_cadastro.php?id=<?php echo $cadastroID ?>"role="button"><i class="far fa-edit"></i>&nbsp;Editar</a></td>


<a class="btn btn-danger"  style="color: #fff"   href="editar_cadastro.php?id=<?php echo $cadastroID ?>"role="button"><<i class="far fa-trash-alt"></i>&nbsp;Deletar</a>
    

    <?php } ?>


    </tr>


</table>
   

_________________________________________________________________________________________________________________
  nome do arquivo
  _inserir_.php
  
 _________________________________________________________________________________________________________________


<?php  

include 'conexao.php';



$nome = $_POST['Nome'];
$telefone = $_POST['Telefone'];
$cidade = $_POST['Cidade'];
$estado = $_POST['Estado'];
$registro = $_POST['tipocadastro'];




 $sql	= "INSERT INTO cadastro ( nome, telefone, cidade, estado,tipocadastro) VALUES ('$nome', '$telefone', '$cidade', '$estado','$registro')";


$inserir = mysqli_query($conexao,$sql);

   $id_nome   





?>

<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.1/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-+0n0xVW2eSR5OomGNYDnhzAbDsOXxcvSN1TPprVMTNDbiYZCxYbOOl7+AMvyTG2x" crossorigin="anonymous">
<div  class="container" style="width: 500px;margin-top: 20px">
     
     <center>
 <h4>cadastro efetuado com sucesso!</h4>
      </center>

             <div style="padding-top: 20px" >
  	  <center>
   
             <a href="index.php" role="button" class="btn btn btn-primary">Cadastrar Novo Ítem</a>
       </center>

</div>

</div>











































</div>













<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.1/dist/js/bootstrap.bundle.min.js" integrity="sha384-gtEjrD/SeCtmISkJkNUaaKMoLD0//ElJ19smozuHV6z3Iehds+3Ulb9Bn9Plx0x4" crossorigin="anonymous"></script>
</body>
</html>


______________________________________________________________________________________________________________________

conexao.php              / nome do arquivo

______________________________________________________________________________________________________________________
  
  <?php

$servname ="localhost"; // padrao serve local.
$username ="root"; // padrão root.
$passoword = "";  //senha de conexão do banco de dados.
$database = "ana"; // alterar conforme o nome do seu banco de dados.
// create connection



// A FUNÇÃO MYSQL CONNECT FOI DESATIVADA // USA MYSQLI ACRESCENTA O i

	// TEM QUE ESTAR NA ORDEM: SERVIDOR-USUARIO-SENHA-BANCO

		//1-(NOME DO SERVIDOR- OK)	$servename ="localhost"; 
		//2-(NOME DO USUARIO)		VF  $username = "root"; 
		//3-(NOME DO SENHA DO BD)   VF  $password =" "; // padrão root.
		//4-(NOME DO BANCO)			VF	$database = "ana";

$conexao = mysqli_connect($servname,$username,$passoword,$database);
	//Forçar o banco a gravar o nome com acento por exemplo: Goiânia e ultilizar UTF-8
	
	mysqli_set_charset ($conexao, "utf8");	

//Testando conexao

	/*if(!$conexao){
	  die("Falha na conexao: " . mysqli_connect_error());
		}else{
		  echo "<center>conexao ok </center>";
	}*/
?>
