---
layout: nice-text
---
  
  ![](img/ryan-v-ryan.jpg)  

## Lorem Ipsum

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

<a href="https://github.com/DS4PS/barebones-jekyll/blob/master/_layouts/liquid-table.html" target = "_blank"> 
          <button onclick="href=''"> See Page Layout <i class="fa fa-github 2x" id="github_icon"></i> </button>
</a>

<hr>


<h2> Ryan vs Ryan: Liquid Table Demo </h2>

<table id="ryan-v-ryan">

<thead>
  <tr>
    <th>  <h3>  Ryan Reynolds  </h3>  </th>
    <th>  <h3>  Ryan Gosling  </h3>  </th>
  </tr>
</thead>

<tbody>

<tr>
  
  
  <td>
  
    
    <h4>  Strengths  </h4>
    <ul>
      
      {% for item in page.reynolds.strengths %}
         <li>{{ item }}</li>
      {% endfor %}
      
    </ul>
    
    <br>

    <h4>  Weaknessess  </h4>
    <ul>
      
      {% for item in page.reynolds.weaknesses %}
         <li>{{ item }}</li>
      {% endfor %}
      
    </ul>  
    
    
  </td>
  


  <td>
  
    <h4>  Strengths  </h4>
    <ul>
      
      {% for item in page.gosling.strengths %}
        <li>{{ item }}</li>
      {% endfor %}
      
    </ul>
    
    <br>
    
    <h4>  Weaknessess  </h4>
    <ul>
      
      {% for item in page.gosling.weaknesses %}
         <li>{{ item }}</li>
      {% endfor %}
      
    </ul>

  </td>
</tr> 

</table>


<br>

<hr>

<br>


<blockquote>
<pre>
<code>

    ###
    ###  LAYOUT INHERITANCE
    ###
    ###  pages built by adding elements 
    ###  to other page layouts 
    ###

          default.html layout 
          │
          └── nice-text.html layout 
              │
              └── liquid-table.html layout
                  # see liquid table below



          ###
          ###  default.html layout
          ###

          &lt;html>
          &lt;head>
            &lt;body>                                
              &lt;header>   

              &lbrace;&lbrace; content }}     

              &lt;footer>           
            &lt;/body>  
          &lt;/html>     

          ###
          ###  &lbrace;&lbrace;content}}
          ###  is replaced by
          ###  whatever content
          ###  is on the page that
          ###  uses the default.html 
          ###  template 
          ###



          ###
          ### nice-text.html layout
          ###

          ---
          layout: default
          ---

          &lt;div class="pretty-text">

          &lt;h1> &lbrace;&lbrace; page.title }} &lt;/h1>

          &lbrace;&lbrace; content }}

          &lt;/div>


          ###
          ### liquid-table.html layout
          ###

          ---
          layout: nice-text
          ---

          &lbrace;&lbrace; content }}

          #  liquid table starts here





    ###
    ###  LIQUID TABLE ADDED USING YAML DATA
    ###
    ###  liquid is a simple markup language that allows
    ###  web designers to separate page layouts from
    ###  page content without databases
    ###
    ###  &lbrace;%  function in liquid  %}
    ###  &lbrace;&lbrace;  variable in liquid  }}
    ###

        ###
        ###  YAML HEADER FOR PAGE
        ###

        ---
        layout: liquid-table
        title: 'amiright?'
        reynolds:
          strengths:
          - good father
          - funny
          - dated alanis morissette
          weaknesses: 
          - singing
          - green lantern movie
          - tennis backhand 
        gosling:
          strengths: 
          - builds houses
          - is a real boy
          - never dated alanis morissette
          weaknesses: 
          - micky mouse club
          - cries a lot
          - not ryan reynolds
        ---

       ###
       ###  LIQUID TAG TABLE IN LAYOUT
       ###
       ###  HTML ELEMENTS: 
       ###  &lt;thead> table header
       ###  &lt;tr>  table row 
       ###  &lt;td>  table cell (or data)
       ###  &lt;ul> unordered list
       ###  &lt;li> list item 
       ###

        &lt;h2> Ryan vs Ryan &lt;/h2>

        &lt;table id="ryan-v-ryan">

        &lt;thead>
          &lt;tr>
            &lt;th>  &lt;h3>  Ryan Reynolds  &lt;/h3>  &lt;/th>
            &lt;th>  &lt;h3>  Ryan Gosling  &lt;/h3>  &lt;/th>
          &lt;/tr>
        &lt;/thead>

        &lt;tbody>
        &lt;tr>
          &lt;td>
            &lt;h4>  Strengths  &lt;/h4>
            &lt;ul>

              ###  LIQUID LOOPS WITH YAML DATA
              ###  reynolds:
              ###    strengths:
              ###    - good father
              ###    - funny
              ###    - dated alanis morissette

              &lbrace;% for item in page.reynolds.strengths %}
                 &lt;li>  &lbrace;&lbrace; item }}  &lt;/li>
              &lbrace;% endfor %}

              ###    LIQUID LOOP CREATES HTML CODES:
              ###    &lt;li> good father &lt;/li>
              ###    &lt;li> funny &lt;/li>
              ###    &lt;li> dated alanis morissette &lt;/li>        

            &lt;/ul>
            &lt;br>
            &lt;h4>  Weaknessess  &lt;/h4>
            &lt;ul>

              &lbrace;% for item in page.reynolds.weaknesses %}
                 &lt;li>  &lbrace;&lbrace; item }}  &lt;/li>
              &lbrace;% endfor %}

            &lt;/ul>  
          &lt;/td>
          &lt;td>
            &lt;h4>  Strengths  &lt;/h4>
            &lt;ul>

              &lbrace;% for item in page.gosling.strengths %}
                &lt;li>  &lbrace;&lbrace; item }}  &lt;/li>
              &lbrace;% endfor %}

            &lt;/ul>
            &lt;br>
            &lt;h4>  Weaknessess  &lt;/h4>
            &lt;ul>

              &lbrace;% for item in page.gosling.weaknesses %}
                 &lt;li>  &lbrace;&lbrace; item }}  &lt;/li>
              &lbrace;% endfor %}

            &lt;/ul>
          &lt;/td>
        &lt;/tr> 
        &lt;/table>

</code>
</pre>
</blockquote>





<style>
  pre{
  font-family: Consolas, Menlo, Monaco, Lucida Console, Liberation Mono, DejaVu Sans Mono, Bitstream Vera Sans Mono, Courier New, monospace, serif;
  margin-bottom: 10px;
  padding: 5px;
  background-color: #eee;
  width: 750px!ie7;
  padding-bottom: 20px!ie7;
}

ui {
  padding-inline-start: 10px;
  }
  
table {
  margin-left: 20px;
  }
  
</style>
