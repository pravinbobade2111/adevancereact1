import React, { useState } from 'react';

const ExpenseForm = () => {
  const [expenseTitle, setExpenseTitle] = useState('');
  const [expenseAmount, setExpenseAmount] = useState('');
  const [expenseDate, setExpenseDate] = useState('');

  const handleInputChange = (e) => {
    // Log input changes to the console
    console.log(e.target.name, e.target.value);

    // Update state based on the input name
    if (e.target.name === 'title') {
      setExpenseTitle(e.target.value);
    } else if (e.target.name === 'amount') {
      setExpenseAmount(e.target.value);
    } else if (e.target.name === 'date') {
      setExpenseDate(e.target.value);
    }
  };

  return (
    <form>
      <label>
        Expense Title:
        <input
          type="text"
          name="title"
          value={expenseTitle}
          onChange={handleInputChange}
        />
      </label>
      <br />
      <label>
        Expense Amount:
        <input
          type="text"
          name="amount"
          value={expenseAmount}
          onChange={handleInputChange}
        />
      </label>
      <br />
      <label>
        Date:
        <input
          type="text"
          name="date"
          value={expenseDate}
          onChange={handleInputChange}
        />
      </label>
      <br />
      <button type="submit">Add Expense</button>
    </form>
  );
};

export default ExpenseForm;

