import streamlit as st
import pickle 
import pandas as pd

st.title("welcome to my LogesticRegression")
model=pickle.load(open("model (1).pkl","rb"))


Age=st.sidebar.number_input("enter the age ")
Fare=st.sidebar.number_input("enter the Fare")
Family=st.sidebar.number_input("enter the Family")
input_val=pd.DataFrame({"Age":[Age],"Fare":[Fare],"Family":[Family]})
st.dataframe(input_val)
pred= model.predict(input_val)
st.write("my predict value:",pred)
st.success("my prediction is successfuly is done ")
if pred ==1 :
    st.write("the people is servived")
else:
    st.write("the people is Died")
