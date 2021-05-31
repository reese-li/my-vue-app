<template>
<div>
  <b-table fixed responsive :items="items" :fields="fields">
      <template #thead-top="">
        <b-tr>
          <b-th colspan="2"><span class="sr-only">Name and ID</span></b-th>
          <b-th variant="secondary">Type 1</b-th>
          <b-th variant="primary" colspan="3">Type 2</b-th>
          <b-th variant="danger">Type 3</b-th>
        </b-tr>
      </template>
    <!-- additional table slots here if needed -->
  </b-table>
  <div>
  <b-table-simple hover small caption-top responsive>
    <caption>Items sold in August, grouped by Country and City:</caption>
    <colgroup><col><col></colgroup>
    <colgroup><col><col><col></colgroup>
    <colgroup><col><col></colgroup>
    <b-thead head-variant="dark">
      <b-tr>
        <b-th colspan="2">Region</b-th>
        <b-th colspan="3">Clothes</b-th>
        <b-th colspan="2">Accessories</b-th>
      </b-tr>
      <b-tr>
        <b-th>Country</b-th>
        <b-th>City</b-th>
        <b-th>Trousers</b-th>
        <b-th>Skirts</b-th>
        <b-th>Dresses</b-th>
        <b-th>Bracelets</b-th>
        <b-th>Rings</b-th>
      </b-tr>
    </b-thead>
    <b-tbody>
      <b-tr>
        <b-th rowspan="3">Belgium</b-th>
        <b-th class="text-right">Antwerp</b-th>
        <b-td>56</b-td>
        <b-td>22</b-td>
        <b-td>43</b-td>
        <b-td variant="success">72</b-td>
        <b-td>23</b-td>
      </b-tr>
      <b-tr>
        <b-th class="text-right">Gent</b-th>
        <b-td>46</b-td>
        <b-td variant="warning">18</b-td>
        <b-td>50</b-td>
        <b-td>61</b-td>
        <b-td variant="danger">15</b-td>
      </b-tr>
      <b-tr>
        <b-th class="text-right">Brussels</b-th>
        <b-td>51</b-td>
        <b-td>27</b-td>
        <b-td>38</b-td>
        <b-td>69</b-td>
        <b-td>28</b-td>
      </b-tr>
      <b-tr>
        <b-th rowspan="2">The Netherlands</b-th>
        <b-th class="text-right">Amsterdam</b-th>
        <b-td variant="success">89</b-td>
        <b-td>34</b-td>
        <b-td>69</b-td>
        <b-td>85</b-td>
        <b-td>38</b-td>
      </b-tr>
      <b-tr>
        <b-th class="text-right">Utrecht</b-th>
        <b-td>80</b-td>
        <b-td variant="danger">12</b-td>
        <b-td>43</b-td>
        <b-td>36</b-td>
        <b-td variant="warning">19</b-td>
      </b-tr>
    </b-tbody>
    <b-tfoot>
      <b-tr>
        <b-td colspan="7" variant="secondary" class="text-right">
          Total Rows: <b>5</b>
        </b-td>
      </b-tr>
    </b-tfoot>
  </b-table-simple>
</div>
  </div>
</template>



<script>
export default {
  data() {
      return {
        items: [
          { name: 'Stephen Hawking', id: 1, type1: false, type2a: true, type2b: false, type2c: false, type3: false },
          { name: 'Johnny Appleseed', id: 2, type1: false, type2a: true, type2b: true, type2c: false, type3: false },
          { name: 'George Washington', id: 3, type1: false, type2a: false, type2b: false, type2c: false, type3: true },
          { name: 'Albert Einstein', id: 4, type1: true, type2a: false, type2b: false, type2c: true, type3: false },
          { name: 'Isaac Newton', id: 5, type1: true, type2a: true, type2b: false, type2c: true, type3: false },
        ],
        fields: [
          'name',
          { key: 'id', label: 'ID' },
          { key: 'type1', label: 'Type 1' },
          { key: 'type2a', label: 'Type 2A' },
          { key: 'type2b', label: 'Type 2B' },
          { key: 'type2c', label: 'Type 2C' },
          { key: 'type3', label: 'Type 3' }
        ]
      }
    },
  created() {},
};
</script>

