{% for product_option in product.options_with_values offset:1 %}
   {% if forloop.index == 1 %}
   {% for value in product_option.values  %}
          <div class="custom-line-property">
         <span class="coffee-select {% if forloop.index == 1 %}coffee-one first_time {% elsif forloop.index == 2 %}coffee-two second_time {% else forloop.index == 3 %}coffee-three third_time{% endif %}" style="display:none;"><h3 class="coffe-bags">Coffee Bag:</h3>  {{ value | split:"/" | last }}</span>
        </div>
        {% endfor %}
{% else %}
 {% for value in product_option.values  %}
   <div class="custom-coffee-type">
         <span class="coffee-select{% if forloop.index == 1 %} coffee-type-one first_time {% elsif forloop.index == 2 %} coffee-type-two second_time {% else forloop.index == 3 %} coffee-type-three third_time {% endif %}" style="display:none;"><h3 class="coffe-bags">Coffee Type:</h3>{{ value | split:"/" | last }}</span>
        </div>
    {% endfor %}
  {% endif %}
    {% endfor %}
